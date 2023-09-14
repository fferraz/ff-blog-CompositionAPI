<template>
  <div class="home">
    <h1> Home </h1>
    <div v-if="error"> {{ error }}</div>
    <div v-if="posts.length">
      <!-- <PostList v-if="showPosts" :posts="posts"/> -->
      <PostList :posts="posts"/>
      
    </div>
    <div v-else> Loading... </div>

    <!-- <button @click="showPosts = !showPosts"> toggle post </button>
    <button @click="posts.pop()"> Delete post </button> -->


  </div>

    <!-- <input type="text" v-model="search">
    <p> search term - {{ search }}</p>
    <div v-for="name in matchingNames" :key="name">
    <p> {{name}} </p>    
    </div>
    <button @click="handleClick"> stop watching </button> -->
    <!-- <p ref="p"> {{ name}}, {{ age }}</p> -->
    <!-- <h2> Refs</h2>
    <p> {{FOne.name}} - {{FOne.age}} </p>
    <h2> Reactive </h2>
    <p> {{ FTwo.name }} - {{ FTwo.age }}</p> 
    <button @click="handleClick"> Click me Ref </button> <br>
    <button @click="handleClickReactive"> Click me Reactive </button> -->
    <!-- <input type="text" v-model="name">
    <button @click="age++"> Add 1 to age</button> -->
</template>

<script>
//import { ref, reactive } from 'vue'

import PostList from '../components/PostList.vue'
import getPosts from '../composables/getPosts'

export default {
  components: { PostList },
  name: 'HomeView',
  // Composition API
  setup(){
    const {posts, error, load} = getPosts()

    load()
    

    return{posts, error}
  }
}
// const names = ref(['mario', 'yoshi', 'luigi', 'toad', 'bowser', 'koopa', 'peach'])
    // const search = ref('')
    // const stopWatch = watch(search, () => {
    //   console.log('watch function')
    // })
    // const stopEffect = watchEffect( () => {
    //   console.log('watch effect', search.value)
    // })
    // const matchingNames = computed(() => {
    //   return names.value.filter( (name) => name.includes(search.value))
    // })
    // const handleClick = () => {
    //   stopWatch()
    //   stopEffect() 
    // }
    // const name = computed(() => {
    //   return 'shaun'
    // })
    // reactive
    //const FOne = ref({name: 'mario', age: 30})
    //const FTwo = reactive({name: 'luigi', age:35})
    //const name = ref('mario')
    //const age = ref(30)
    //let name = 'mario'
    //let age = 30
    //const handleClick = () => {
      //FOne.value.age = 40
      // console.log(p, p.value)
      // p.value.classList.add('test')
      // p.value.textContent = 'hello lol'
    //}
    //const handleClickReactive = () => {
    //  FTwo.age = 40
    //}
    //const p = ref('hello')
    //console.log(p,p.value)
    //return{FOne, handleClick, FTwo, handleClickReactive}
  // data(){
  //   return{
  //     score: 5
  //   }
  // }

</script>


    
