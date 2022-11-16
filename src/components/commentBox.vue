<script>
export default {

}
</script>

<template>
    <div class="panel">
        <div class="panel__info">
            <p class="panel__username"><strong>Elon Tusk</strong></p>
            <p class="panel__subtext">No space on Subway Station</p>
        </div>
        <div class="comment__view">
            <div class="comment__iterate">
                <p class="comment__username"><strong>wajoo</strong></p>
                <p class="comment__txt">i am txt</p>
            </div>
        </div>
        <div class="comment__interaction">
            <input type="text" id="message" name="message" placeholder="message...">
            <button class="comment__button">send</button>
        </div>
    </div>
</template>

<style scoped>
input {
    width: 300px;
    height: 30px;
}

.panel {
    padding: 2em 0;
    text-align: left;
    margin: 1em;
    height: 80vh;
    width: 30%;
    background-color: white;
    color: #1a1a1a;
}

.comment__iterate {
    display: flex;
    flex-direction: row;
    gap: 2em;
}

.panel__info {
    margin: 0em 1em;
    height: 10vh;
    height: fit-content;
}

.comment__view {
    padding: 0em 1em;
    height: 60vh;
    background-color: #f4f0e8;
}

.comment__interaction {
    padding: 0em 1em;
    display: flex;
    flex-direction: row;
    align-items: center;
    height: 10vh;
    background-color: white;
}

.comment__interaction {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    gap: 1em;
}

.panel__username {
    margin: 0;
}
</style>