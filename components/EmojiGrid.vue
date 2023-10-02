<template>
    <div class="container grid grid-cols-12">
        <div v-for="emoji in emojis" class="emoji-btn" @click="copyToClipboard(emoji.emoji)">
            <h1>{{ emoji.emoji }}</h1>
        </div>
    </div>
    <!-- <div>Copied to clipboard!</div> -->
</template>

<script setup>
import { groups, subgroups, hierarchy } from 'emojibase-data/meta/groups.json';
import emojis from 'emojibase-data/en/data.json';

const copyToClipboard = (text) => {
    const textarea = document.createElement('textarea');
    textarea.value = text;
    document.body.appendChild(textarea);
    textarea.select();
    document.execCommand('copy');
    document.body.removeChild(textarea);
}
</script>
