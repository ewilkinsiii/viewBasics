# viewBasics
- Stucture
  ```Javascript
    new Vue({
      //el tell it that it can interact with objects inside of the div class
    el:'#app',
    data: {
      title: 'Becoming a Vue Ninja',
      object: {
        contains1: 'value',
        contains2: 0,
      }
    },
    // methods can interact with data
    methods: {
      methods: {
      greet(time){
        return `Hello and good ${time}, ${this.name}`
      }
    }
  })
  ```
- Methods
  ```Javascript
   methods: {
    greet(time){
      return `Hello and good ${time}, ${this.name}`
    }
  }
  ```
  ```html
   <p> {{greet('morning')}}</p>
  ```
  ### Results: 
  ```html
   <p> Hello and good morning, Ryu</p> 
  ```
- Data Binding
  ```Javascript
    data: {
    title: 'Becoming a Vue Ninja',
    name: 'Ryu',
    url: 'https://www.youtube.com/',
    classes: ['one', 'two']
  },
  ```
  ```html
   <a v-bind:href="url">YouTube</a>
   <div :class="classes">Classes from Instance</div>
   <!--using : is the same as v-bind:-->
  ```
  ### Results
  ```html
    <a href="https://www.youtube.com/">YouTube</a>
    <div class="one two">Classes from Instance</div>
  ```
  
- Events
  ```html
    <p>I earn {{wage}} pounds per hour</p>
    <button v-on:dblclick="wage++">Increase wage by 1 </button>
    <button v-on:dblclick="wage--">Decrease wage by 1 </button>
    <!--using a method-->
    <button v-on:click="changeWage(1)">Increase wage by 1 </button>
    <button v-on:click="changeWage(-1)">Decrease wage by 1 </button>
    <!--double click using a method-->
     <button v-on:dblclick="changeWage(5)">Increase wage by 5 </button>
    <button v-on:dblclick="changeWage(-5)">Decrease wage by 5 </button>
  ```
  ```Javascript
   data: {
    title: 'Becoming a Vue Ninja',
    wage: 10
  },
  methods: {
   changeWage(amount){
     this.wage += amount
   }
  }
  ```
- Event Objects
  ```html
     <!-- @ is a short cut for v-on-->
     <button @click='logEvent'>Log Event Info</button>
     <div class="canvas" @mousemove="logCoords">{{coords.x}}, {{coords.y}}</div>
  ```
  ```Javascript
     data: {
    title: 'Becoming a Vue Ninja',
    coords: {
      x:0,
      y: 0,
    }
  },
  methods: {
    // e represents the event object
    logEvent(e){
      console.log(e)
    },
    // the event object has a offsetX and Y which is the position of your mouse on the screen
    logCoords(e){
      this.coords.x = e.offsetX
      this.coords.y = e.offsetY
    }
  }
  ```
- Keyboard Events
  ```Javascript
  data: {
    title: 'Becoming a Vue Ninja',
    name: 'Ryu'
  },
  methods: {
    updateName(e){
      //console.log(e.target.value)
      // brings back the value that you've entered
      this.name = e.target.value
    }
  }
  ```
  ```html
    <!--Updates instantly-->
     <input type="text" @keyup="updateName">
     <!--Always one press behind-->
    <input type="text" @keypress="updateName">
  ```