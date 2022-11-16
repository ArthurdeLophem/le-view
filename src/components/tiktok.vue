<script>
export default {

}
</script>

<template>
    <div class="video__container">
        <video class="video" controls autoplay muted src="https://vue-3-tiktok.vercel.app/video2.mp4"></video>
    </div>
</template>

<style scoped>
.video__container,
.video {
    height: 90vh;
    width: fit-content;
    border-radius: 10px;
}
</style>