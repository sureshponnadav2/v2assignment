<template>
  <div class="container">
    <!-- find city and state -->

    <h2>Find City & State</h2>

    <label for="input">Enter ZipCode:</label>
    <input
      type="text"
      name="inputValue"
      id="zip"
      @keyup.enter="getData()"
      v-model="inputZipValue"
    /><br /><br />
    <button type="button" v-on:click="getData()">Get Data</button><br /><br />
    <h5>{{ StateName }}</h5>
    <h5>{{ cityName }}</h5>
    <h5>{{ error }}</h5>

    <!-- increment and decrement -->

    <h2>Increment and Decrement</h2>
    <h3>Counter: {{ counter }}</h3>
    <button type="button" v-on:click="increment()">increment</button>

    <button type="button" v-on:click="decrement()">decrement</button>

    <!-- reverse the words in the Sentence -->
    <h2>reverse the words in the Sentence</h2>
    Enter Sting:
    <input
      @keyup.enter="string(inputString)"
      v-model="inputString"
      type="text"
      name="inputString"
      id="inputString"
    />
    <br /><br />
    <button type="button" v-on:click="string(inputString)">Click</button>
    <br /><br />
    {{ revSentence }}

    <!-- Div Section assignment -->
    <h1>Div Section assignment</h1>
    <button type="button" v-on:click="htmlCss()">Click Me</button>
  </div>
</template>

<script>
//import axios from "axios";

export default {
  data() {
    return {
      name: "suresh!!!",
      inputZipValue: "",
      error: "",
      cityName: "",
      StateName: "",
      counter: 0,
      inputString: "",
      revSentence: "",
      // detailsData: [] // data stores in this API respose success
      details: {
        City: "LOS ANGELES",
        State: "CA",
        Latitude: 33.973593,
        Longitude: -118.247897,
        ZipCode: "90001",
        County: "LOS ANGELES",
      },
      createDiv: [
        { height: 100, width: 100 },
        { height: 75, width: 75 },
        { height: 50, width: 50 },
        { height: "suresh", width: 25 },
      ],
    };
  },
  methods: {
    getData() {
      if (this.inputZipValue == this.details.ZipCode) {
        // console.log(`${this.details.City}, ${this.details.State}`);
        this.cityName = `City: ${this.details.City}`;
        this.StateName = `State: ${this.details.State}`;
      } else {
        // console.log(this.error);
        this.error = `Invalid ZipCode`;
      }
    },

    increment() {
      // console.log(`I am working!`);
      this.counter = this.counter + 1;
    },
    decrement() {
      // console.log(`I am working!`);
      this.counter = this.counter - 1;
    },
    string(arg) {
      this.inputString = arg;
      let collectrevString = [];
      // let revWords = arg.split(" ").reverse().join(" ");
      // // console.log(revWords);
      // this.revSentence = revWords;
      let len = arg.length;
      //console.log(this.inputString)
      for (let i = len - 1; i >= 0; i--) {
              
        if(arg[i] == ' '){
          var revValStr = collectrevString.reverse().join('');
        }
         collectrevString.push(arg[i]);
       
      }

     console.log(revValStr);
    },
    htmlCss() {
      console.log(this.createDiv[0].height);
      // JSON.stringify(filters);
    },
  },
};
</script>

<style scoped>
</style>