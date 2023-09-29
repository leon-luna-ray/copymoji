<template>
    <div class="container grid grid-cols-12">
        <div v-for="emoji in emojis.nature" class="emoji-btn" @click="copyToClipboard(emoji)">
            <span>
                {{ emoji }}
            </span>
        </div>
    </div>
    <div>Copied to clipboard!</div>
</template>

<script setup>
import { emojis } from '../lib/emojis'

const copyToClipboard = (text) => {
    const textarea = document.createElement('textarea');
    textarea.value = text;
    document.body.appendChild(textarea);
    textarea.select();
    document.execCommand('copy');
    document.body.removeChild(textarea);
}
</script>
