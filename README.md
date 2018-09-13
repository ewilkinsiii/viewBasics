# viewBasics
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