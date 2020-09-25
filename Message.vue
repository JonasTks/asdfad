<template>
    <div>
        <input type="text" v-model="message" @keyup.enter ="add">
        <button @click="add">Add</button>
        <button @click="items = []">Clear list</button>
        <item-lists title="All items" :items="items"></item-lists>
        <item-lists title="Done items" :items="doneItems"></item-lists>
        <item-lists title="Not Done items" :items="notDoneItems"></item-lists>
    </div>
</template>
<script>
import ItemsList from './ItemsList.vue';
import example from './example.vue';
export default {
    components: {
        example: example,
        'item-lists': ItemsList,
    },
    mounted(){
        this.$alert("Welcome retard"); 
    },
    data(){
        return {
            somevalue: "helloworld",
            lastId: 3,
            message: "",
            items:[
            {title:'Viin', isDone: false, id:1},
            {title:'Kanep', isDone: true, id:2},
            {title:'Tups', isDone: false, id:3}
            ],
        }
    }, 
    methods: {
        add(){
            if(this.message != "") {
            this.items.push({title: this.message, isDone: false, id: this.lastId ++});
            this.message="";
            }
        },

    },
    computed:{
        doneItems(){
            return this.items.filter(item => item.isDone);
        },
        notDoneItems(){
            return this.items.filter(item => !item.isDone);
        },

    }
}
</script>
