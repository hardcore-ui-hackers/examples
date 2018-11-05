<template>
    <div class="eda-button">
        <div class="eda-button__i">
            <a href="#prizes" class="eda-button__link">
                <div class="eda-button__link-wrapper">
                    <span class="eda-button__link-text">Розыгрыш</span>
                </div>
                <div class="eda-button__shadow"></div>
            </a>
        </div>
    </div>
</template>

<style lang="less">
    .eda-button {
        display: inline-block;

        &__i {
            z-index: 1;
            padding-right: 6px;
            padding-bottom: 6px;
            overflow: hidden;
            transition: color .2s ease-in-out; /* hover effect */
            color: green;

            &:hover {
                color: blue;
            }
        }

        &__link-wrapper {
            background-color: yellow;
            transition: background-color .2s ease-in-out;
        }

        &__link {
            position: relative;
            display: block;
            color: inherit;
            text-decoration: none !important; /* !important due to Vuepress default styles */

            &::after,
            &::before {
                position: absolute;
                z-index: -1;
                content: "";
                width: 0;
                height: 0;
                border-style: solid
            }

            &::before {
                right: -6px;
                top: 0;
                border-width: 6px 0 0 6px;
                border-color: transparent transparent transparent currentColor;
            }

            &::after {
                bottom: -6px;
                left: 0;
                border-width: 0 6px 6px 0;
                border-color: transparent currentColor transparent transparent;
            }

            &:active {
                transform: translate(6px, 6px)
            }
        }

        &__link,
        &__link::after,
        &__link::before {
            transition: transform .2s ease-in-out; /* pressing effect */
        }

        &__link-text {
            font-size: 24px;
            line-height: 50px;
            padding: 0 2em;
        }

        &__shadow {
            position: absolute;
            z-index: -1;
            background-color: currentColor;
            top: 6px;
            left: 6px;
            right: -6px;
            bottom: -6px
        }
    }
</style>