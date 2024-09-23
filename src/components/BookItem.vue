<template>
    <div class="bookCard">
        <img class="bookImage" :src="image" />
        <h3 class="bookTitle">{{ title }}</h3>
        <h4 class="bookAuthor">{{ author }}</h4>
        <slot name="genre"></slot>
        <slot name="rating"></slot>

        <div id="bookSelected">
            <button class="bookButton" @click="$emit('bookSelected', title)">
                Select
            </button>
        </div>
    </div>
</template>


<script>
export default {
    props: ['image', 'title', 'author'],
    emits: ['bookSelected']
}
</script>