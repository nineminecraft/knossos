<template>
  <div class="content">
    <Head>
      <Title> {{ project.title }} - Changelog </Title>
      <Meta name="og:title" :content="`${props.project.title} - Changelog`" />
      <Meta name="description" :content="metaDescription" />
      <Meta name="apple-mobile-web-app-title" :content="`${props.project.title} - Changelog`" />
      <Meta name="og:description" :content="metaDescription" />
    </Head>
    <VersionFilterControl
      :versions="props.versions"
      @update-versions="
        (v) => {
          filteredVersions = v
          switchPage(1)
        }
      "
    />
    <Pagination
      :page="currentPage"
      :count="Math.ceil(filteredVersions.length / 20)"
      class="pagination-before"
      :link-function="(page) => `?page=${page}`"
      @switch-page="switchPage"
    />
    <div class="card">
      <div
        v-for="version in filteredVersions.slice((currentPage - 1) * 20, currentPage * 20)"
        :key="version.id"
        class="changelog-item"
      >
        <div
          :class="`changelog-bar ${version.version_type} ${version.duplicate ? 'duplicate' : ''}`"
        />
        <div class="version-wrapper">
          <div class="version-header">
            <div class="version-header-text">
              <h2 class="name">
                <nuxt-link
                  :to="`/${props.project.project_type}/${
                    props.project.slug ? props.project.slug : props.project.id
                  }/version/${encodeURI(version.displayUrlEnding)}`"
                >
                  {{ version.name }}
                </nuxt-link>
              </h2>
              <span v-if="version.author">
                by
                <nuxt-link class="text-link" :to="'/user/' + version.author.user.username">{{
                  version.author.user.username
                }}</nuxt-link>
              </span>
              <span>
                on
                {{ $dayjs(version.date_published).format('MMM D, YYYY') }}</span
              >
            </div>
            <a
              :href="version.primaryFile.url"
              class="iconified-button download"
              :title="`Download ${version.name}`"
            >
              <DownloadIcon aria-hidden="true" />
              Download
            </a>
          </div>
          <div
            v-if="version.changelog && !version.duplicate"
            class="markdown-body"
            v-html="renderHighlightedString(version.changelog)"
          />
        </div>
      </div>
    </div>
    <Pagination
      :page="currentPage"
      :count="Math.ceil(filteredVersions.length / 20)"
      class="pagination-before"
      :link-function="(page) => `?page=${page}`"
      @switch-page="switchPage"
    />
  </div>
</template>
<script setup>
import DownloadIcon from '~/assets/images/utils/download.svg'
import { renderHighlightedString } from '~/helpers/highlight'
import VersionFilterControl from '~/components/ui/VersionFilterControl'
import Pagination from '~/components/ui/Pagination'

const props = defineProps({
  project: {
    type: Object,
    default() {
      return {}
    },
  },
  versions: {
    type: Array,
    default() {
      return []
    },
  },
  members: {
    type: Array,
    default() {
      return []
    },
  },
})

const metaDescription = computed(
  () => `View the changelog of ${props.project.title}'s ${props.versions.length} versions.`
)

const route = useRoute()
const currentPage = ref(Number(route.query.p ?? 1))
const filteredVersions = shallowRef(props.versions)

async function switchPage(page) {
  currentPage.value = page

  const router = useRouter()
  const route = useRoute()

  await router.replace({
    query: {
      ...route.query,
      p: currentPage.value !== 1 ? currentPage.value : undefined,
    },
  })
}
</script>

<style lang="scss">
.changelog-item {
  display: block;
  margin-bottom: 1rem;
  position: relative;
  padding-left: 1.8rem;

  .changelog-bar {
    --color: var(--color-special-green);

    &.alpha {
      --color: var(--color-special-red);
    }

    &.release {
      --color: var(--color-special-green);
    }

    &.beta {
      --color: var(--color-special-orange);
    }

    left: 0;
    top: 0.5rem;
    width: 0.2rem;
    min-width: 0.2rem;
    position: absolute;
    margin: 0 0.4rem;
    border-radius: var(--size-rounded-max);
    min-height: 100%;
    background-color: var(--color);

    &:before {
      content: '';
      width: 1rem;
      height: 1rem;
      position: absolute;
      top: 0;
      left: -0.4rem;
      border-radius: var(--size-rounded-max);
      background-color: var(--color);
    }

    &.duplicate {
      background: linear-gradient(
        to bottom,
        transparent,
        transparent 30%,
        var(--color) 30%,
        var(--color)
      );
      background-size: 100% 10px;
    }

    &.duplicate {
      height: calc(100% + 1.5rem);
    }
  }

  .version-header {
    display: flex;
    align-items: center;
    margin-top: 0.2rem;

    .circle {
      min-width: 0.75rem;
      min-height: 0.75rem;
      border-radius: 50%;
      display: inline-block;
      margin-right: 0.25rem;
    }

    .version-header-text {
      display: flex;
      align-items: baseline;
      flex-wrap: wrap;

      h2 {
        margin: 0;
        font-size: var(--font-size-lg);
      }

      h2,
      span {
        padding-right: 0.25rem;
      }
    }

    .download {
      display: none;

      @media screen and (min-width: 800px) {
        display: flex;
      }
    }

    .markdown-body {
      margin: 0.5rem 0.5rem 0 0;
    }
  }
}
</style>