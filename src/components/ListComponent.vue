<template>
<div>
    <li v-for="(item, key, index) in items">
        {{key}} - {{item.message}}
    </li>
    <li v-for="n in evenNumbers"> {{ n }}</li>

    <button class="btn-button" @click="count++"> add 1</button>
    <button class="btn-button" @click="count--"> subtractive 1</button>
    <button class="btn-button" @click="say('hello')">Say hello</button>
    <button class="btn-button" @click="say('bye')">Say bye</button>
    <button class="btn-button" @click="warn('Form cannot be submitté yet.', $event)">Submit</button>
    <button class="btn-button" @click.stop="doThis">Submit</button>
    <p> Count is : {{ count }}</p>
    <!-- /input -->
    <h1>message is: {{ text }}</h1>
    <input v-model.trim="text" placeholder="edit me">
    <!-- checkbox -->
    <input type="checkbox" id="NTA" value="NTA" v-model="checkboxNames"/>
    <label for="NTA">NTA</label>
    <input type="checkbox" id="NB" value="NB" v-model="checkboxNames"/>
    <label for="NB">NB</label>
    <input type="checkbox" id="NC" value="NC" v-model="checkboxNames"/>
    <label for="NC">NC</label>
    <div> checked name: {{ checkboxNames }}</div>

    <!-- radio button -->
    <input type="radio" id='one' value="one" v-model="picked" />
    <label for="one">One</label>
    <input type="radio" id='two' value="two" v-model="picked" />
    <label for="two">Two</label>

    <div> picked: {{ picked }}</div>

    <!-- selection  -->
    <select v-model="selected">
        <option v-for="(option, key, index) in options" :value="option.value">{{ option.text}}</option>
    </select>
    <div> Selected: {{ selected }}</div>

    <!-- binding checkbox -->
    <input 
      type="checkbox"
      v-model="toggle"
      true-value="yes"
      false-value="no"/>
</div>
  
</template>

<script>
export default {
    data() {
        return {
            items: [{message:'abc'}, {message:'xyz'}, {message:'jon'}, {message: 'anh van'}],
            numbers: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
            count: 1,
            text: 0,
            checkboxNames: [],
            picked:'',
            selected : 'A',
            options: [
                {text: 'One', value: 'A'},
                {text: 'Two', value: 'B'},
                {text: 'Three', value: 'C'},
            ]
        }
    },
    methods : {
        say(message) {
            alert(message)
        },
        warn(message, event) {
            if (event) {
                event.preventDefault()
            }
            alert(message)
        },
        doThis() {
            alert(this.count)
        }
    },
    computed : {
        evenNumbers() {
            return this.numbers.filter(n => n % 2 === 0).reverse()
        }
    }
}
</script>

<style>
.btn-button {
    margin: 0 auto;
    padding: 10px 20px;
    color:blue;
    background: white;
    border-radius: 5px;
    border: 1px solid blue;
    box-shadow: 0 0 5px;
}
.btn-button:hover {
    color:yellowgreen;
    background: blue;
    transform: translateY(2px);
    
}
.button{
    width:100%;
    text-align: center;
    margin: 20px 0;
}
</style>