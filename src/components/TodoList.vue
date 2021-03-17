<template>
  <div class="todolist">
    <div class="todoitem" v-for="(todo, index) in todos" :key="index">
        <label class="todolabel" >{{ todo.description }}</label>
        <Button icon="pi pi-pencil" class="p-button-rounded p-button-text" @click="$emit('edit', index)" />
        <Button icon="pi pi-trash" class="p-button-rounded p-button-text" @click="$emit('delete', index)" />
    </div>
  </div>
</template>

<script>

export default {
    props: {
        todos: Array
    }
}
</script>

<style scoped>
 .todolist {
     margin: 1rem;
 }
 .todoitem {
     display: flex;
     align-items: center;
     border-bottom: 1px solid lightgray;
 }
 .todolabel {
     flex-grow: 1;
 }
</style>