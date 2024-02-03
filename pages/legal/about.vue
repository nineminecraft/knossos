<template>
    <div class="markdown-body">
        <h1> About nineMinecraft </h1>
        <h2> Let's clear the air on what this is. </h2>

        <h1 id="why-do-you-scam-people">Why do you scam people???</h1>
        <p>We don&#39;t. nineMinecraft is not affiliated with 9Minecraft. We are instead mainly a scam alert, but we have
            this part of our website (dev.nineminecraft.com) which is a <strong>Modrinth mirror</strong> and has no illegal
            or stolen content.<br>
            Nothing here is for profit, there are no ads and we don&#39;t try to monetize on Modrinth&#39;s creators works.
            This is mainly a fun project for the devs behind it to learn about Knossos, and make a funcional website based
            on it.</p>
        <h1 id="what-is-nineminecraft">What is nineMinecraft?</h1>
        <p>As seen in the main page, it&#39;s a scam alert. It is also technically a mod hosting website, since this page on
            the site <strong>uses the official Modrinth prod API.</strong><br>
            This will never become anything when speaking of mod hosting websites, or mod stealing websites. Our goal is to
            steal 9Minecraft&#39;s SEO so we can let people know about the dangers of 9minecraft.<br>
            <i style="text-decoration: wavy line-through"> it also makes us be able to have an unbranded base for any other
                Knossos project ~~ </i>
        </p>
        <h2 id="the-main-website">The main website</h2>
        <p>The main website is <a href="https://nineminecraft.com">https://nineminecraft.com</a>, and you can clearly see
            the original purpose of the website.
            <img src="~/assets/images/about/nineminecrafthome.png" alt="Image of nineMinecraft's homepage">
        </p>
        <h2 id="the-mod-pages">The mod pages</h2>
        <p>Some projects have pages on nineminecraft.com with full permission, such as <a
                href="https://nineminecraft.com/mod/pridepack">pridepack</a> and <a
                href="https://nineminecraft.com/mod/pixelpack">pixelpack</a>, which don&#39;t really serve much purpose but
            maybe steal even more SEO from 9minecraft to point to a safe source.
            <img src="~/assets/images/about/pridepackmodpage.png" alt="Image of PridePack's nineMinecraft page">
        </p>
        <h2 id="the-knossos-website">The Knossos website</h2>
        <p>Its where you are now! It&#39;s a very modified website based on <a
                href="https://modrinth.com">Modrinth</a>&#39;s <a href="https://github.com/modrinth/knossos">Knossos</a>
            frontend. It uses modrinth&#39;s official production API, which means everything that is on Modrinth as a
            project is also here.<br>
            Everything you download will still count as a download to the original creator, although unfortunately, they
            won&#39;t get any revenue from it as we had to remove <a href="https://Adrinth.com">Adrinth</a>.<br>
            You can&#39;t sign in or create projects through here, but downloading is still fully supported.
            <img src="~/assets/images/about/nineminecraftknossos.png" alt="An image of nineMinecraft's knossos instance.">
        </p>

        <h2> Who made this? </h2>

        nineMinecraft is managed by <a href="https://blurryface.xyz">Blurryface</a> and <a
            href="https://worldwidepixel.ca">WorldWidePixel</a>.

        <h2> Thank you for reading</h2>

        <p>That&#39;s all. If we make new stuff we will update this page!</p>
        <p><em><strong>Last modified on February 2nd 2024</strong></em></p>

    </div>
</template>
  
<script setup>

const description =
    'About nineMinecraft, an open-source modding thing.'

useSeoMeta({
    title: 'About nineMinecraft - nineMinecraft',
    description,
    ogTitle: 'About nineMinecraft',
    ogDescription: description,
})
</script>

<style>
img {
    border-radius: 1rem;
    margin-top: 1rem;
}
</style>