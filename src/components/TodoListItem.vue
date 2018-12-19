<template>
    <li>
        {{todo.text}}
        <button v-on:click="$emit('remove', todo.id)">
            &#9587;
        </button>
    </li>
</template>

<script>
/* eslint-disable */
export default {
    props:{
        //타입은 오브젝트이고, 꼭 필요합니다.
        todo: {
            type: Object,
            required: true
        }
    }
}
</script>
