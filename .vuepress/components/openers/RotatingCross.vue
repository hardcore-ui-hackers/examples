<template>
    <div class="rotating-сross-wrapper">
        <div v-on:click="animateButton" class='rotating-сross'></div>
    </div>
</template>

<style lang="less">

    .rotating-сross-wrapper {
        background-color: black;
        width: 58px;
        padding: 10px 20px;
        margin: 30px 0;
    }

    .rotating-сross {
        display: inline-block;
        width: 1em;
        height: 1em;
        border: 0.08em solid lighten(gold, 20%);
        font-size: 3em;
        border-radius: 50%;
        position: relative;
        transition-duration: 0.5s;
        cursor: pointer;

        &:before {
            content: "";
            display: block;
            position: absolute;
            background-color: lighten(gold, 20%);
            width: 80%;
            height: 5%;;
            left: 10%;
            top: 47%;
        }

        &:after {
            content: "";
            display: block;
            position: absolute;
            background-color: lighten(gold, 20%);
            width: 5%;
            height: 80%;
            left: 47%;
            top: 10%;
        }

        &.open {
            background-color: lighten(gold, 20%);
            &:after {
                background-color: black;
            }
            &:before {
                background-color: black;
            }
        transform: rotate(225deg);
        }
    }
</style>

    <script lang="javascript">
    export default {
        methods: {
            animateButton(e) {
                e.preventDefault();
                e.target.classList.toggle('open');
            }
        }
    }
</script>
