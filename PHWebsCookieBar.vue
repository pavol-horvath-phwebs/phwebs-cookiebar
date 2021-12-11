<template>
    <div class="phwebs-cookie-bar">
        <span class="phwebs-cookie-bar-text">
            Tieto stránky používajú cookies. Prehliadaním stránok súhlasíte s ich používaním.
        </span>
        <span class="phwebs-cookie-bar-succes" v-on:click="clickSucces()">
            Súhlasím
        </span>
    </div>
</template>

<script>
import Vue from 'vue'
import VueCookies from 'vue-cookies'
Vue.use(VueCookies)

export default {
    data() {
        return {
            success: false
        }
    },
    methods: {
        clickSucces() {
            this.success = true
            Vue.$cookies.set('phwebs-cookie-success', true, '1y', '/')
        }
    },
    created() {
        if (Vue.$cookie.get('phwebs-cookie-success')) {
            this.success = true
        }
    }
}
</script>

<style lang="less" scoped>
.phwebs-cookie-bar {
    position: absolute;
    bottom: 0.5em;
    left: 50%;
    transform: translateX(-50%);
    padding: 1em;
    border-radius: 0.5em;
    background: fadeout(#7d7d7d, 30%);
    .phwebs-cookie-bar-succes {
        padding: 0.5em;
        margin-left: 1em;
        border-radius: 0.5em;
        background: #fa0098;
        cursor: pointer;
        font-weight: bold;
    }
}
</style>