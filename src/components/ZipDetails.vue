<template>
  <div class="container">
    <!-- find city and state -->
<div class="col">
      <h2>Find City & State</h2>

    <label for="input">Enter ZipCode: </label>
    <input
      type="text"
      name="inputValue"
      id="zip"
      @keyup.enter="getData()"
      v-model="inputZipValue"
    />
    <button type="button" v-on:click="getData()">Get Data</button>
    <h5>{{ StateName }}</h5>
    <h5>{{ cityName }}</h5>
    <h5>{{ error }}</h5>
</div>


    <!-- increment and decrement -->
<div class="col increment-block">
      <h2>Increment and Decrement</h2>
    <h3>Counter: {{ counter }}</h3>
    <button type="button" v-on:click="increment()">increment</button>

    <button type="button" v-on:click="decrement()">decrement</button>
</div>


    <!-- reverse the words in the Sentence -->
    <div class="col">
          <h2>reverse the words in the Sentence</h2>
    Enter Sting:
    <input
      @keyup.enter="string(inputString)"
      v-model="inputString"
      type="text"
      name="inputString"
      id="inputString"
    />
    
    <button type="button" v-on:click="string(inputString)">Click</button>
    
  <h5> {{ revSentence }}</h5>
  <h5> {{ strError }}</h5>
    </div>

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
      strError: "",
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
      if( arg == ''){
        this.strError = `Invalid  Input`
      }else{
       //  this.inputString = arg;
      let revWords = arg.split(" ").reverse().join(" ");
      console.log(revWords);
      this.revSentence = revWords;
      }
     

    },
   
  }
};
</script>

<style scoped>
.container{
display: flex;
    margin: 20px;
    background: #fbfbfb;
   padding: 42px 22px;
    border-radius: 28px;
    box-shadow: 0 0 7px 2px #aeb1b3;
}
.container button {
    padding: 12px;
    font-weight: 400;
    border: 1px solid #f44336;
    background: #f44336;
    color: #fff;
    margin-right: 22px;
    text-transform: uppercase;
    border-radius: 7px;
}
.container button:hover {
    background: transparent;
        cursor: pointer;
    color: #f44336;
}
input:focus-visible {
    outline: 0;
    box-shadow: 0 0 3px #f44336;
    border: 0px solid;
}
.container input {
   padding: 10px 10px;
    border-radius: 5px;
    width: 60%;
    border: 1px solid #f44336;
    margin-bottom: 14px;
}
.col {
    text-align: center;
}
.container .col {
    width: 100%;
}
.container h2 {
    font-weight: 500;
    font-size: 20px;
    text-transform: capitalize;
    text-align: center;
}
.increment-block h3{
  margin-bottom: 26px;
}

</style>