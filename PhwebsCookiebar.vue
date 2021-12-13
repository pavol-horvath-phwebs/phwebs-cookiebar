<template>
    <div v-if="!success" class="phwebs-cookiebar">
        <div class="phwebs-cookiebar-text">
            Tieto stránky používajú cookies. Prehliadaním stránok súhlasíte s ich používaním.
        </div>
        <div class="phwebs-cookiebar-succes" v-on:click="clickSucces()">
            Súhlasím
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            success: false
        }
    },
    methods: {
        clickSucces() {
            this.success = true
            this.$cookie.set('phwebs-cookie-success', true)
        }
    },
    created() {
        if (this.$cookie.get('phwebs-cookie-success')) {
            this.success = true
        }
    }
}
</script>

<style lang="less" scoped>
.phwebs-cookiebar {
    position: fixed;
    bottom: 0.5em;
    left: 50%;
    transform: translateX(-50%);
    padding: 1em;
    margin: auto;
    margin-top: 0.5em;
    width: fit-content;
    border-radius: 0.5em;
    background: fadeout(#7d7d7d, 10%);
    .phwebs-cookiebar-text {
        color: #eeeeee;
    }
    .phwebs-cookiebar-succes {
        padding: 0.5em;
        border-radius: 0.5em;
        background: #fa0098;
        cursor: pointer;
        font-weight: bold;
        &:hover {
            background-color: darken(#fa0098, 10)
        }
    }
}
</style>