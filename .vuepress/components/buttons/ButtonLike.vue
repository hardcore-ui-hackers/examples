<template>
    <a v-on:click="animateButton" class='like-button'>
        <span class='like-button__icon'>
            <div class='heart-animation-1'></div>
            <div class='heart-animation-2'></div>
        </span>
        Like
    </a>
</template>

<style lang="less">

    .like-button {
        cursor: pointer;
        text-decoration: none !important;
        border: 2px solid #c7c7c7;
        border-radius: 40px;
        padding: .45rem .75rem;
        color: darken(#c7c7c7, 25%);
        font-weight: bold;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 1rem;
        transition: all .25s cubic-bezier(.175, .885, .32, 1.275);
        filter: grayscale(100%);
        width: 100px;
        margin: 50px 0 30px 0;

        &.liked {
            color: #ff6e6f;
            border-color: currentColor;
            filter: grayscale(0);
        }

        &:hover {
            border-color: currentColor;
            text-decoration: none;
        }

        &__icon {
            width: 18px;
            height: 16px;
            display: inline-block;
            position: relative;
            margin-right: .25em;
            font-size: 1.5rem;
            background: url('data:image/svg+xml;utf8,<svg width="21" height="18" viewBox="0 0 21 18" xmlns="http://www.w3.org/2000/svg"><title>heart-colored</title><path d="M10.101 4.417S8.895.207 5.111.207c-4.465 0-10.967 6.846 5.082 17.592C25.237 7.03 19.665.202 15.501.202c-4.162 0-5.4 4.215-5.4 4.215z" fill="#FF6E6F" fill-rule="evenodd"/></svg>') no-repeat center;
            background-size: 100%;
            animation: heartUnlike .25s cubic-bezier(.175, .885, .32, 1.275) both;
        }
    }

    .liked .like-button__icon {
        animation: heartPulse .25s cubic-bezier(.175, .885, .32, 1.275) both;

        [class^="heart-animation-"] {
            background: url('data:image/svg+xml;utf8,<svg width="21" height="18" viewBox="0 0 21 18" xmlns="http://www.w3.org/2000/svg"><title>heart-colored</title><path d="M10.101 4.417S8.895.207 5.111.207c-4.465 0-10.967 6.846 5.082 17.592C25.237 7.03 19.665.202 15.501.202c-4.162 0-5.4 4.215-5.4 4.215z" fill="#FF6E6F" fill-rule="evenodd"/></svg>') no-repeat center;
            background-size: 100%;
            display: block;
            position: absolute;
            top: 0;
            left: 0;
            width: 16px;
            height: 14px;
            opacity: 0;

            &::before, &::after {
                content: '';
                background: inherit;
                background-size: 100%;
                width: inherit;
                height: inherit;
                display: inherit;
                position: relative;
                top: inherit;
                left: inherit;
                opacity: 0;
            }
        }

        .heart-animation-1 {
            animation: heartFloatMain-1 1s cubic-bezier(.175, .885, .32, 1.275) both;

            &::before, &::after {
                width: 12px;
                height: 10px;
                visibility: hidden;
            }
            &::before {
                opacity: .6;
                animation: heartFloatSub-1 1s .25s cubic-bezier(.175, .885, .32, 1.275) both;
            }
            &::after {
                animation: heartFloatSub-2 1s .15s cubic-bezier(.175, .885, .32, 1.275) both;
                opacity: .75;
            }
        }

        .heart-animation-2 {
            animation: heartFloatMain-2 1s .1s cubic-bezier(.175, .885, .32, 1.275) both;

            &::before, &::after {
                width: 10px;
                height: 8px;
                visibility: hidden;
            }
            &::before {
                animation: heartFloatSub-3 1s .25s cubic-bezier(.175, .885, .32, 1.275) both;
                opacity: .25;
            }
            &::after {
                animation: heartFloatSub-4 1s .15s cubic-bezier(.175, .885, .32, 1.275) both;
                opacity: .4;
            }
        }
    }


    // Animations
    @keyframes heartPulse {
        0% {
            transform: scale(1);
        }
        50% {
            transform: scale(1.5);
        }
    }

    @keyframes heartUnlike {
        50% { transform: scale(.75) ; }
    }

    @keyframes heartFloatMain-1 {
        0% {
            opacity: 0;
            transform: translate(0) rotate(0);
        }
        50% {
            opacity: 1;
            transform: translate(0, -25px) rotate(-20deg);
        }
    }

    @keyframes heartFloatMain-2 {
        0% {
            opacity: 0;
            transform: translate(0) rotate(0) scale(0);
        }
        50% {
            opacity: .9;
            transform: translate(-10px, -38px) rotate(25deg) scale(1);
        }
    }

    @keyframes heartFloatSub-1 {
        0% {
            visibility: hidden;
            transform: translate(0) rotate(0);
        }
        50% {
            visibility: visible;
            transform: translate(13px, -13px) rotate(30deg);
        }
    }

    @keyframes heartFloatSub-2 {
        0% {
            visibility: hidden;
            transform: translate(0) rotate(0);
        }
        50% {
            visibility: visible;
            transform: translate(18px, -10px) rotate(55deg);
        }
    }

    @keyframes heartFloatSub-3 {
        0% {
            visibility: hidden;
            transform: translate(0) rotate(0);
        }
        50% {
            visibility: visible;
            transform: translate(-10px, -10px) rotate(-40deg);
        }
        100% {
            transform: translate(-50px, 0);
        }
    }

    @keyframes heartFloatSub-4 {
        0% {
            visibility: hidden;
            transform: translate(0) rotate(0);
        }
        50% {
            visibility: visible;
            transform: translate(2px, -18px) rotate(-25deg);
        }
    }
</style>

<script lang="javascript">
    export default {
        methods: {
            animateButton(e) {
                e.target.classList.toggle('liked');
            }
        }
    }
</script>
