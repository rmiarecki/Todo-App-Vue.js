<template>

    <div>
      

      
      <div class="new-item" >
        <!-- <p>New To Do: {{newItem}}</p> -->
        <input type="text" placeholder="Create new todo" v-model="newItem" >
        <button @click="addItem">Add</button>
      </div>
      <ToDoAppItem  
        v-for="item in items" 
        v-bind:key="item.id" 
        v-bind:item="item"
        @removeClicked="removeItem"
        />
    </div>

</template>
  
<script>
  import ToDoAppItem from './ToDoAppItem.vue'
  
  export default {
    components: {
        ToDoAppItem
    },
    data() {
      return {
        newItem: '',
        items: [
          {tittle: 'Practice CSS for 2 hours', completed: false, id: 1},
          {tittle: 'Practice Vue.js for 2 hours', completed: true, id: 2}
        ]
        
      }
    },
    methods: {
      addItem() {
        this.items.push({
          tittle: this.newItem, 
          completed: false, 
          id: Math.random()
        })
        this.newItem = ''
      },
      removeItem(id) {
        const index = this.items.findIndex(el => el.id === id)
        this.items[index].completed = true
      }
    }
  }
  
</script>