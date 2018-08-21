<template>
  <div>
    <button type="button" class="btn btn-success" @click="newNote">Create</button>
    <button type="button" class="btn btn-danger" @click="deleteNote">Delete</button>
  </div>
</template>

<script>
  export default {
    data: function () {
      return {}
    },
    methods: {
      newNote() {
        this.$store.state.notes.push(this.$store.state.notes.length + 1);
      },
      deleteNote() {
        this.$store.state.notes.pop();
      }
    }
  }
</script>

<style scoped>
  div{
    border-radius: 10px;
    border:1px solid green;
    background: lawngreen;
    width: 250px;
    height: 150px;
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 30px auto;
  }
  button{
    margin: 10px;
  }
</style>

