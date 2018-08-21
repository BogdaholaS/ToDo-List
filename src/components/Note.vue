<template>
  <div class="noteBlock">
    <div>
      <div class="result" v-if="!isActive">{{note}}</div>
      <transition name="slide2" appear v-else>
        <div class="editing form-group">
          <input type="text" class="form-control" v-model="note">
        </div>
      </transition>
    </div>
    <div class="buttons">
        <button type="button" class="btn btn-success" @click="isActive = false">Save</button>
        <button type="button" class="btn btn-primary" @click="isActive = true">Edit</button>
        <button type="button" class="btn btn-danger" @click="deleteThis">Delete</button>
    </div>
  </div>
</template>

<script>
  export default {
    data: function () {
      return {
        isActive:true,
        note:''
      }
    },
    methods: {
      deleteThis() {
        this.$emit("deleting")
      }
    }
  }
</script>

<style>
  .noteBlock{
    border-radius: 10px;
    border:1px solid green;
    background: lawngreen;
    width: 250px;
    height: 150px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin: 30px auto;
  }
  .result{
    margin-bottom: 10px;
  }
</style>
