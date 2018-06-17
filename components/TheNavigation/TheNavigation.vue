<template>
    <header class="border-t-2 border-black">
        <nav class=" flex content-center justify-between p-4 container mx-auto">
            <nuxt-link tag="div" to="/" data-name="logo" class="">
                <a class="no-underline text-black"><h1>Phoebe</h1></a>
            </nuxt-link>
            <div data-name="nav-links" class="">
                <nuxt-link to="/" tag="li"
                    class="inline-block mx-4">
                    <a class="leading-loose no-underline text-black">All</a>
                </nuxt-link>
                <nuxt-link to="/blog/" tag="li"
                    class="inline-block mx-4 relative border">
                    <a class="leading-loose no-underline text-black">Blog</a>
                </nuxt-link>
                <nuxt-link to="/video/" tag="li"
                    class="inline-block mx-4">
                    <a class="leading-loose no-underline text-black">Video</a>
                </nuxt-link>
                <!--<nuxt-link to="/about" tag="li"
                    class="inline-block px-4">
                    <a class="leading-loose no-underline">About</a>
                </nuxt-link>-->
                <li
                    class="inline-block mx-4">
                    <span class="leading-loose no-underline cursor-pointer">Social</span>
                </li>
            </div>
        </nav>
    </header>
</template>