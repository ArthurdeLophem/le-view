<script setup>
import { ref, reactive, onMounted } from 'vue';
let comments = reactive([{ messages: "" }]),
    message = ref('');

const getMessages = () => {
    fetch('https://lab5-p379.onrender.com/api/v1/messages/')
        .then((response) => response.json())
        .then((data) => {
            console.log(data);
            comments.messages = data
        });
}

const addMessage = () => {
    let username = document.querySelector(".panel__username").innerText;
    const newMessage = {
        user: username,
        text: message.value
    }
    fetch('https://lab5-p379.onrender.com/api/v1/messages/', {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify(newMessage)
    }).then((response) => response.json())
        .then((data) => {
            console.log(data);
        });
    // comments.messages.push(newMessage)
    // console.log(comments)
}

onMounted(() => {
    getMessages()
})

</script>

<template>
    <div class="panel">
        <div class="panel__info">
            <p class="panel__username"><strong>Elon Tusk</strong></p>
            <p class="panel__subtext">No space on Subway Station</p>
        </div>
        <div class="comment__view">
            <ul class="comment__list">
                <li v-for="comment in comments.messages" class="comment__iterate" :key="comment">
                    <p class="comment__username"><strong>{{ comment.user }}</strong></p>
                    <p class="comment__txt">{{ comment.text }}</p>
                </li>
            </ul>
        </div>
        <div class="comment__interaction">
            <input type="text" id="message" name="message" placeholder="message..." v-model="message">
            <button class="comment__button" @click="addMessage">send</button>
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
    overflow-y: scroll;
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