<template>
  <div>
    <h1>Assignments</h1>
    <v-select v-model="subject" :items="items" 
    label="เลือกรายวิชา" solo></v-select>
    <v-text-field v-model="work" :items="items" label="ใส่รายละเอียดในรายวิชา" solo></v-text-field>
    <center><v-btn color="#00C853" class="mr-4"  @click="addTodo()">เพิ่ม</v-btn></center><br>
    <v-contai>
      
    <v-card class="mx-auto" max-width="344" outlined v-for="(item, i) in additems" :key="i" >
    

      <v-list-item-content>
        <center><v-list-item-subtitle>{{item.text1}}</v-list-item-subtitle></center><br>
        
      </v-list-item-content>
  

    <v-card-actions>
      <v-btn  color="#00C853"  @click="deleteTodo(i)">Delete</v-btn>
    </v-card-actions>
    </v-card> 
  
    </v-contai>
    
  </div>
</template>

<script>
export default {
  data() {
    return{
      subject:"",
      work:"",
      items: ['ศท242', 
      'คพ313', 
      'สต301', 
      'คพ232', 
      'ศส', 
      'cs343', 
      'MC'],
      selectedItem: 1,
      additems: [
        { text1: 'วิชา Web '+'Assignments : 1 '},
        { text1: 'วิชา SA'+'Assignments : 2 ' },
        { text1: 'วิชา ML '+'Assignments : 3 '},
        { text1: 'วิชา Web '+'Assignments : 4 '},
        
      ],
      
    }
  },
  methods:{
    addTodo(){
      this.additems.push({ text1:this.subject+this.work});
    },
    deleteTodo(index){
      this.additems.splice(index,1);
      
    },
  },
};
</script>

<style></style>
