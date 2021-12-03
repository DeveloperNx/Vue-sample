<template>
  <div>
    <link href="https://cdn.jsdelivr.net/npm/animate.css@3.5.1" rel="stylesheet" type="text/css">
    <b-form @submit.prevent="onsubmit" v-if="show">

      <div id="example-3">
  <button @click="show4 = !show4">
    Toggle render
  </button>
  <transition
    name="custom-classes-transition"
    enter-active-class="animated tada"
    leave-active-class="animated bounceOutRight"
  >
    <p v-if="show4">hello</p>
  </transition>
</div>




      <!-- v-on:click -->
      <div id="app-5">
  <p>{{ message2 }}</p>
  <button v-on:click="reverseMessage">Reverse Message</button>
</div>

<!-- only v-if -->
<div id="app-3">
  <span v-if="seen">Now you see me</span>
</div>

<!-- v-for loop -->
<ul id="example-1">
  <li v-for="item in items" :key="item.message">
    {{ item.message }}
  </li>
</ul>

<!-- v-for with second argument  -->
<ul id="example-2">
  <li v-for="(item, index) in itemss" :key="item.message">
    {{ parentMessage }} - {{ index }} - {{ item.message }}
  </li>
</ul>

<!-- v-for with object -->
<ul id="v-for-object" class="demo">
  <li v-for="(value, name) in object" :key="value.name">
     {{ name }}: {{ value }}
  </li>
</ul>

<!-- v-for -->
<li v-for="n in evenNumbers" :key="n">{{ n }}</li>

  <!-- <ul>
    <template v-for="item in items">
      <li>{{ item.msg }}</li>
      <li class="divider" role="presentation"></li>
    </template>
  </ul> -->

  <!-- <li v-for="todo in todos" v-if="!todo.isComplete">
  {{ todo }}
</li>
 -->
 <!-- <my-component v-for="item in items" :key="item.id"></my-component> -->

<!--  <div id="todo-list-example">
  <form v-on:submit.prevent="addNewTodo">
    <label for="new-todo">Add a todo</label>
    <input
      v-model="newTodoText"
      id="new-todo"
      placeholder="E.g. Feed the cat"
    >
    <button>Add</button>
  </form>
  <ul>
    <li
      is="todo-item"
      v-for="(todo, index) in todos"
      v-bind:key="todo.id"
      v-bind:title="todo.title"
      v-on:remove="todos.splice(index, 1)"
    ></li>
  </ul>
</div>
 -->


<br>
<br>
<div id="example-1">
  <button @click="show2 = !show2">
    Toggle render
  </button>
  <transition name="slide-fade">
    <p v-if="show2">hello</p>
  </transition>
</div>
<br>
<br>

 <br>
<br>
<div id="demo">
  <button v-on:click="show1 = !show1">
    Toggle
  </button>
  <transition name="fade">
    <p v-if="show1">hello</p>
  </transition>
</div>
<br><br>
 <!-- listening event-->
 <div id="example-1">
  <button v-on:click="counter += 1">Add 1</button>
  <p>The button above has been clicked {{ counter }} times.</p>
</div>

<!-- bootstrap component -->
    <b-form-group id="input-group-1" label="Email address:" label-for="input-1" description="We'll never share your email with anyone else.">

        <b-form-input id="input-1" v-model="form.email" type="email" placeholder="Enter email" required >
         </b-form-input>
         </b-form-group>

        <b-form-group id="input-group-2" label="Name:" label-for="input-2">

        <b-form-input id="input-2" v-model="form.name" type="text" placeholder="Enter Name" required >
         </b-form-input>
         </b-form-group>

        <b-form-group id="input-group-3" label="Food:" label-for="input-3" >
        <b-form-select
          id="input-3" 
          v-model="form.food"
          :options="foods"
          required
        ></b-form-select>
         </b-form-group>

        <b-form-group id="input-group-4" >
        <b-form-checkbox-group id="checkboxes-4" v-model="form.checked">

          <b-form-checkbox value="me">Check me out</b-form-checkbox>
          <b-form-checkbox value="that">Check that out</b-form-checkbox>
        </b-form-checkbox-group>
      </b-form-group>

       <b-form-group label="Individual radios">
      <b-form-radio v-model="form.selected" value="A">Option A</b-form-radio>
      <b-form-radio v-model="form.selected"  value="B">Option B</b-form-radio>
    </b-form-group>

    <div class="mt-3">Selected: <strong>{{ form.selected }}</strong></div>

    <label for="example-datepicker">Choose a date</label>
    <b-form-datepicker id="example-datepicker" v-model="form.value" class="mb-2"></b-form-datepicker>
    <p>Value: '{{ form.value }}'</p>

    <b-form-file
      v-model="form.file1"
      :state="Boolean(form.file1)"
      placeholder="Choose a file or drop it here..."
      drop-placeholder="Drop file here..."
    ></b-form-file>
    <div class="mt-3">Selected file: {{ form.file1 ? form.file1.name : '' }}</div>

    <!-- Plain mode -->
    <b-form-file v-model="form.file2" class="mt-3" plain></b-form-file>
    <div class="mt-3">Selected file: {{ form.file2 ? form.file2.name : '' }}</div>

    <b-form-group
      id="fieldset-1"
      description="Let us know your name."
      label="Enter your name"
      label-for="input-1"
      valid-feedback="Thank you!"
      :invalid-feedback="invalidFeedback"
      :state="state"
    >
      <b-form-input id="input-1" v-model="name" :state="state" trim></b-form-input>
    </b-form-group>

    <b-form-select v-model="selected" :options="options"></b-form-select>
    <b-form-select v-model="selected" :options="options" size="sm" class="mt-3"></b-form-select>
    <div class="mt-3">Selected: <strong>{{ selected }}</strong></div>

    <label for="demo-sb">Spin Button</label>
    <b-form-spinbutton id="demo-sb" v-model="form.spinvalue" min="1" max="100"></b-form-spinbutton>
    <p>Value: {{ form.spinvalue }}</p>

    <b-form-group
      label="Textarea with formatter (on input)"
      label-for="textarea-formatter"
      description="We will convert your text to lowercase instantly"
      class="mb-0"
    >
      <b-form-textarea
        id="textarea-formatter"
        v-model="text1"
        placeholder="Enter your text"
        :formatter="formatter"
      ></b-form-textarea>
    </b-form-group>
    <p style="white-space: pre-line"><b>Value:</b> {{ text1 }}</p>

    <b-button v-b-modal.modal-1>Launch demo modal</b-button>

  <b-modal id="modal-1" title="BootstrapVue">
    <p class="my-4">Hello from modal!</p>
  </b-modal> 
  <br>
  <br>
<!-- for whitespace  -->
  <input v-model="msg">
<br><br>
  <div id="app">
  {{ message }}
</div>

<button v-on:click="$emit('enlarge-text', 0.1)">
  Enlarge text
</button>

<div id="app-2">
  <span v-bind:title="message1">
    Hover your mouse over me for a few seconds
    to see my dynamically bound title!
  </span>
</div>

<!-- v-if -->
<h1 v-if="awesome">Vue is awesome!</h1>

<!-- v-if v-else -->
<h1 v-if="awesome1">Vue is awesome!</h1>
<h1 v-else>Oh no 😢</h1>

<!-- v-if  template-->
<template v-if="ok">
  <h1>Title</h1>
  <p>Paragraph 1</p>
  <p>Paragraph 2</p>
</template>

<!-- v-if  v-else-->
<div v-if="Math.random() > 0.5">
  Now you see me
</div>
<div v-else>
  Now you don't
</div>

<!-- v-if v-else-if v-else -->

<div v-if="type === 'A'">
  A
</div>
<div v-else-if="type === 'B'">
  B
</div>
<div v-else-if="type === 'C'">
  C
</div>
<div v-else>
  Not A/B/C
</div>
<br>
<br>
<!-- <div id="example-4">
  <button @click="show = !show">
    Toggle
  </button>
  <transition
    v-on:before-enter="beforeEnter"
    v-on:enter="enter"
    v-on:leave="leave"
    v-bind:css="false"
  >
    <p v-if="show">
      Demo
    </p>
  </transition>
</div>
<br>
<br>
 -->

<template v-if="loginType === 'username'">
  <label>Username</label>
  <input placeholder="Enter your username">
</template>
<template v-else>
  <label>Email</label>
  <input placeholder="Enter your email address">
</template>

<!-- v-show with template -->
<template v-show="ok1">Hello!</template>

<!-- v-show with h1 -->
<h1 v-show="ok2">Hello!</h1>

<!-- v-for -->
<div>
  <span v-for="n in 5" :key="n">{{ n }} </span>
</div>

<!--methon  event handlers v-on:click -->
<div id="example-2">
  <!-- `greet` is the name of a method defined below -->
  <button v-on:click="greet">Greet</button>
</div>

<!--method inline event handler v-on-click -->
<div id="example-3">
  <button v-on:click="say('hi')">Say hi</button>
  <button v-on:click="say('what')">Say what</button>
</div>

<!-- event modifires -->
 <button v-on:click.stop="warn('do This.',$event)">Stop</button>
event 
 <button v-on:click="warn1('Form cannot be submitted yet.', $event)">
  Submit
</button>



<br>
<br>
<input v-model.number="age" type="number">

<br>
<br>
<input v-model="searchText">

<br>
<br>

<!-- <BlogPost title="My journey with Vue"></BlogPost> -->
<BlogPost v-bind:title="post.title"></BlogPost>

<div v-bind:id="rawId | formatId"></div>

<br><br>
    
      <b-button type="submit" variant="primary">Submit</b-button>
      <b-button type="reset" variant="danger">Reset</b-button>
    </b-form>
    <b-card class="mt-3" header="Form Data Result">
      <pre class="m-0">{{ form }}</pre>
    </b-card>
  </div>

</template>

<script>
import BlogPost from '../components/BlogPost.vue'
  export default{
    name: 'HelloWorld',
  components: {
   BlogPost,
  },
    computed: {
      state() {
        return this.name.length >= 4
      },
      invalidFeedback() {
        if (this.name.length > 0) {
          return 'Enter at least 4 characters.'
        }
        return 'Please enter something.'
      },
      evenNumbers: function () {
    return this.numbers.filter(function (number) {
      return number % 2 === 0
    })
  },
  animatedNumber: function() {
      return this.tweenedNumber.toFixed(0);
    }
    },
    filters: {
  capitalize: function (value) {
    if (!value) return ''
    value = value.toString()
    return value.charAt(0).toUpperCase() + value.slice(1)
  }
}
  //   watch: {
  //   number: function(newValue) {
  //     gsap.to(this.$data, { duration: 0.5, tweenedNumber: newValue });
  //   }
  // },
    data(){
      return{
        form:{
          email:'',
          name:'',
          food:null,
          checked:[],
           selected:'',
           value:'',
           file1: null,
        file2: null,
        spinvalue: 100, 


        
        },
        post:{

          title:'My journey with Vue'

        },

     

       
    //      number: 0,
    // tweenedNumber: 0,
    show4:true,
        show1:true,
         name1: 'Vue.js',
      counter: 0,
        // sets: [[ 1, 2, 3, 4, 5 ], [6, 7, 8, 9, 10]],
       numbers: [ 1, 2, 3, 4, 5, 6 ],
        object: {
      title: 'How to do lists in Vue',
      author: 'Jane Doe',
      publishedAt: '2016-04-10'
    },
         parentMessage: 'Parent',
    itemss: [
      { message: 'Foo' },
      { message: 'Bar' },
      { message: 'car' }
    ],

         items: [
      { message: 'Foo' },
      { message: 'Bar' },
     
    ],

    show2:true,
        seen: true,
        message2: 'Hello Vue.js!',
        message1: 'You loaded this page on ' + new Date().toLocaleString(),
        message: 'Hello Vue!',
        text1: '',
        text2: '',
        awesome: true,
        awesome1:false,
        ok:true,
        Math: 0.8,
        type:'A',
        loginType:'username',
        ok1:true,
searchText:'',
        ok2:true,

        age:'',
         name: '',
msg:'',
emit:'hi',
         selected: null,

          posts: [
      { id: 1, title: 'My journey with Vue' },
      { id: 2, title: 'Blogging with Vue' },
      { id: 3, title: 'Why Vue is so fun' }
    ],
        options: [
          { value: null, text: 'Please select an option' },
          { value: 'a', text: 'This is First option' },
          { value: 'b', text: 'Selected Option' },
          { value: { C: '3PO' }, text: 'This is an option with object value' },
          { value: 'd', text: 'This one is disabled', disabled: true }
        ],
        foods: [{ text: 'Select One', value: null},'carrots','tomatoes'],
        show:true
      }
    },
        


    methods:{
      onsubmit(e){
        e.preventDefault()
         alert(JSON.stringify(this.form))

      },
      formatter(value) {
        return value.toLowerCase()
      },
      reverseMessage: function () {
      this.message2 = this.message2.split('').reverse().join('')
    },
  //    evenNumbers: function () {
  //   return this.numbers.filter(function (number) {
  //     return number % 2 === 0
  //   })
  // },
    greet: function (event) {
      // `this` inside methods points to the Vue instance
      alert('Hello ' + this.name1 + '!')
      // `event` is the native DOM event
      if (event) {
        alert(event.target.tagName)
      }
    },
     say: function (message) {
      alert(message)
    },

    warn: function (message, event) {
    // now we have access to the native event
    if (event) {
      event.preventDefault()
    }
    alert(message)
  },

  warn1: function(message, event) {
    if(event){
      event.preventDefault()
    }
    alert(message)
  },


    
    }



  }

</script>
<style>
.fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}

.slide-fade-enter-active {
  transition: all .3s ease;
}
.slide-fade-leave-active {
  transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateX(10px);
  opacity: 0;
}
 </style>