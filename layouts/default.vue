<template>
    <div>
        <header>
            <nav
                class="container mx-auto p-4 py-5 flex justify-between items-center text-sm"
            >
                <NuxtLink to="/">
                    <img src="/logo.png" class="h-[25px]" />
                </NuxtLink>

                <ul class="hidden sm:flex gap-5">
                    <li><NuxtLink to="/solutions">Solutions</NuxtLink></li>
                    <li><NuxtLink to="/services">Services</NuxtLink></li>
                    <li><NuxtLink to="/about">About</NuxtLink></li>
                    <li><NuxtLink to="/contact-us">Contact us</NuxtLink></li>
                </ul>
            </nav>
        </header>

        <!-- Output page content -->
        <div class="container mx-auto px-4 text-sm">
            <slot />
        </div>
    </div>
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Albert+Sans:wght@300;400;500;600;700&display=swap");
</style>