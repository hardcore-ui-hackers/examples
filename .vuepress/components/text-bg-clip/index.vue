<template>
    <div class="masked-text">
        <div class="masked-text__text">Hello world</div>
    </div>
</template>

<style lang="less">
.masked-text {
    color: orange;

    &__text {
        font-size: 40px;
        font-weight: bold;
        display: inline;
    }
}

@supports (-webkit-background-clip: text) {
    .masked-text {
        background-image: url(./copy_texture_large.jpg);
        background-repeat: no-repeat;
        -webkit-background-clip: text;
        color: transparent !important
    }
}
</style>