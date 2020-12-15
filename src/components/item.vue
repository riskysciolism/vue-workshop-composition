<template>
<div class='view'>
    <input class='toggle' type='checkbox' 
    v-on:click='complete' v-bind:checked='todo.complete'>
    <label>{{todo.title}}</label>
    <button class='destroy' v-on:click='remove'></button>
</div>
</template>

<script lang='ts'>
import { defineComponent, PropType } from 'vue';
import Todo from '../types/todo';

export default defineComponent({
    name: 'item',
    props: {
        todo : {type: Object as PropType<Todo>, required: true}
    },
    setup(props, context) {
        const todo: Todo = props.todo;

        function remove() {
            context.emit('remove', props.todo);
        }

        function complete() {
            context.emit('complete', props.todo);
        }

        return {
            remove,
            complete
        }

    }
})
</script>