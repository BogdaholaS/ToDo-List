<template>
  <div class="container text-center">
    <transition name="fade" appear>
      <create-note></create-note>
    </transition>
    <transition-group name="slide">
      <note
        v-for="(number, index) in this.$store.state.notes"
        :key="index + 1"
        @deleting="deleteNote(index)">
      </note>
    </transition-group>
  </div>
</template>

<script>
  import CreateNote from "./components/CreateNote.vue";
  import Note from "./components/Note.vue";
  export default {
    methods: {
      deleteNote(index) {
        console.log(index);
        this.$store.state.notes.splice(index,1)
      }
    },
    components: {
      createNote:CreateNote,
      note:Note
    }
  }
</script>

<style>
  body{
    font-family: 'Roboto', sans-serif;
    background: greenyellow;
  }
  .fade-enter-active, .fade-leave-active {
    transition: all 1s;
  }
  .fade-enter, .fade-leave-to  {
    opacity: 0;
  }
  .slide-enter-active, .slide-leave-active {
    transition: all .5s;
  }
  .slide-enter, .slide-leave-to  {
    transform: translateX(-200px);
    opacity: 0;
  }
  .slide2-enter-active{
    transition: all .5s;
  }
  .slide2-leave-active {
    transition: 0s;
  }
  .slide2-enter, .slide2-leave-to  {
    transform: translateX(-200px);
    opacity: 0;
  }
</style>
