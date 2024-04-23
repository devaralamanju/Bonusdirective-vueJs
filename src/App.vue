<template>
<div>

<h2>{{ name }}</h2>  
<button @click="name = 'devarala'">Change name</button>

<h2 v-once>{{ changename }}</h2>  
<button @click="name = 'ashu'">Change name</button>


<h2 v-pre>{{ prename }}</h2>  
 <button @click="name = 'ashu'">Change name</button>

 <h2>Full name - {{ firstname }} {{ lastname }}</h2>

 <h2>Computed FullName - {{ fullName }}</h2>

 <button @click="changeFullName">Change Full Name </button>

 <!-- <h2>Total - {{ items.reduce(total, curr) => (total + curr.price), 0 }}</h2> -->
 <h2>Total - {{ totalPrice }}</h2>

<button @click="items.push({id: 4, title: 'keyboard', ptrice : 50})">Add item</button>
 <h2>Computed Total - {{ total }}</h2>
 <h2>Method Total- {{ getTotal() }}</h2>
<input type="text" v-model="country">

<template>

</template>


</div>
</template>

<script>
export default {
  name: 'App',
  data(){
    return {
      name: 'Manju',
      changename: 'maha',
      prename: 'dudu',
      firstname: 'manjula',
      lastname: 'devarala',
      items: [
        {
          id:1,
          title:'TV',
          price:100,
        },
        {
          id:2,
          title:'TV',
          price:100,
        },
        {
          id:3,
          title:'Phone',
          price:200,
        },
        {
          id:4,
          title:'Laptop',
          price:300,
        }
      ]
    }
  },
  methods :{
getTotal(){
  return this.items.reduce((total, curr) => total + curr.price, 0);
},
changeFullName(){
  this.fullName = 'mancha manjula'
}
  },
computed: {
  fullName() {
    return `${this.firstname} ${this.lastname}`
  },
  totalPrice() {
      return this.items.reduce((total, curr) => total + curr.price, 0);
    },
    country:'',
    set(value){
      const names = value.split(' ')
      this.firstname =  names[0]
      this.lastname = names[1]
    }
}
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
