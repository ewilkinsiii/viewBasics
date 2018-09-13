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