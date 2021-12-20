<template>
    <header class="_header">
        <div class="_wrapper">
            <div class="_row-center _header-row">
                <div class="_col">
                    <nuxt-link class="header-logo" to="/">
                        <img src="~/assets/images/logo-header.png" alt="Blog Logo">
                    </nuxt-link>
                </div>
                <div class="_col txt-right">
                    <nuxt-link class="header-link" to="login">
                        LOGIN
                    </nuxt-link>
                </div>
            </div>
        </div>
    </header>
</template>

<style lang="scss" scoped>
    @import '~/assets/scss/header.scss';
</style>