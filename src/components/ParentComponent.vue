<template>
    <div class="parent">
      <h2 class="header">Parent Components</h2>
      <textarea name="" id="" cols="30" rows="10">{{ message }}</textarea>
      <button @click="showChild = true" class="open-modal-button">Child Component</button>
      <Modal v-if="showChild" @close="showChild = false">
        <ChildComponent @childEvent="updateMessage" />
      </Modal>
    </div>
  </template>
  
  <script>
  import ChildComponent from './ChildComponent.vue';
  import Asset from './Asset.vue';
  
  export default {
    name: 'ParentComponent',
    components: {
      ChildComponent,
      Asset,
    },
    data() {
      return {
        message: 'This is the Parent Component',
        showChild: false,
      };
    },
    methods: {
      updateMessage(newMessage) {
        this.message = newMessage;
      },
    },
  };
  </script>
  
  <style scoped>
  
  .parent {
    padding: 20px;
    border: 2px solid #3c0058;
    border-radius: 10px;
    background-color: #3c0058 !important;
    transition: all 0.3s ease;
    height: 85%;
  }
  
  .parent:hover {
    background-color: #3c0058;
  }
  
  textarea {
    width: 97%;
    padding: 10px;
    font-family: 'Times New Roman', Times, serif;
    font-size: 18px;
    border: 2px solid #3c0058;
    border-radius: 5px;
    resize: vertical;
    margin-bottom: 10px;
    text-align: center;
    background-color: #3c0058;
    color: #ffffff;
    height: 100px;
  }
  
  .header {
    font-size: 20px;
    color: #ffffff;
  }
  
  .open-asset-button {
    padding: 10px 20px;
    background-color: #3c0058;
    color: #000000;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
  
  .open-asset-button:hover {
    background-color: #3c0058;
  }
  
  </style>./Asset.vue