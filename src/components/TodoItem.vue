<template>
  <InputText v-model="description" />
  <div class="botoes">
    <Button @click="save">Salvar</Button>
    <Button class="voltar" @click="cancel">Cancelar</Button>
  </div>
</template>

<script>

export default {
    data() {
      return {
          description: ""
      }  
    },
    props:{
      todo: Object
    },
    created() {
        if (this.todo) {
            this.description = this.todo.description;
        }
    },
  methods: {
    cancel() {
      this.$emit("cancel");
    },
    save() {
        this.$emit("save", { ...this.todo, description: this.description } );
    }
  }
}
</script>

<style scoped>
 .botoes {
     margin-top: 1rem;
 }
 .voltar {
     margin-left: 1rem;
 }
</style>