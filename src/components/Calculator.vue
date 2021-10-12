<template>
  <div class="body">
    <div class="container">
      <div class="display">
        <input type="text" placeholder="0" v-model="calVal" />
      </div>

      <div class="btns">
        <button
          v-on:click="calculate(item)"
          class="btn"
          v-for="item in calculatorButtonVal"
          :key="item"
        >
          {{ item || 0 }}
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Calculator",
  data() {
    return {
      calVal: "",
      calculatorButtonVal: [
        "CE",
        "X!",
        "(",
        ")",
        "%",
        "AC",
        "sin",
        "ℼ",
        7,
        8,
        9,
        "/",
        "cos",
        "log",
        4,
        5,
        6,
        "*",
        "tan",
        "√",
        1,
        2,
        3,
        "-",
        "e",
        "x^2",
        "0",
        ".",
        "=",
        "+",
      ],
    };
  },

  methods: {
    // factorial(n) {
    //   if (n == 0) return 1;
    //   return n * factorial(n - 1);
    // },
    calculate(n) {
      if (
        [
          "0",
          1,
          2,
          3,
          4,
          5,
          6,
          7,
          8,
          9,
          ".",
          "+",
          "-",
          "*",
          "/",
          "(",
          ")",
        ].includes(n)
      ) {
        this.calVal += n;
      }

      //   console.log(this.calVal, typeof this.calVal);

      // Cleare Value
      if (n === "AC") {
        this.calVal = "";
      }

      // Percentage
      if (n === "%") {
        this.calVal = this.calVal / 100;
      }

      //   calculate result using eval function
      if (n === "=") {
        this.calVal = eval(this.calVal);
      }

      // Calculate Sin value
      if (n === "sin") {
        this.calVal = Math.sin(this.calVal);
      }

      //Calculate Cos value
      if (n === "cos") {
        this.calVal = Math.cos(this.calVal);
      }

      //Calculate Tan Value
      if (n === "tan") {
        this.calVal = Math.tan(this.calVal);
      }

      // calculate square root of the number
      if (n === "√") {
        this.calVal = Math.sqrt(this.calVal, 2);
      }

      //calculate square of the number
      if (n === "x^2") {
        this.calVal = Math.pow(this.calVal, 2);
      }

      //calculate log value
      if (n === "log") {
        this.calVal = Math.log(this.calVal, 2);
      }

      // use Pi valu in calculation
      if (n === "ℼ") {
        this.calVal = 3.14159265359;
      }

      // use E value in calculation
      if (n === "e") {
        this.calVal = 2.71828182846;
      }

      // calculate factorial
      if (n === "X!") {
        var num = 1;
        for (let i = 1; i <= this.calVal; i++) {
          num *= i;
        }

        this.calVal = num;
      }

      // trim last entry
      if (n === "CE") {
        this.calVal = this.calVal.substr(0, this.calVal.length - 1);
      }
    },
  },
};
</script>

<style>
.body {
  padding: 0;
  margin: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 90vh;
  background: #d0d0d0;
}

.container {
  width: 40%;
  height: 45vh;
  max-width: 500px;
  min-width: 500px;
  max-height: 300px;
  padding: 15px;
  border-radius: 5px;
  background: #f0f0f0;
  box-shadow: 6px 6px 10px gainsboro, -6px -6px 10px gainsboro;
}

.display input {
  /* display: flex;
  align-items: center;
  justify-content: flex-end; */
  width: 97%;
  height: 70px;
  font-size: 36px;
  outline: none;
  border: none;
  text-align: right;
  padding-right: 10px;
  border-radius: 5px;
  background: #ecf0f3;
  box-shadow: inset 8px 8px 8px #cbced1, inset -8px -8px 8px #fff;
}

.btns {
  width: 100%;
  height: 200px;
  margin-top: 25px;
  display: flex;
  flex-direction: row;
  flex-flow: wrap;
  justify-content: center;
  align-items: center;
}

.btn {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 73px;
  height: 30px;
  font-size: 16px;
  border: none;
  outline: none;
  margin: 5px;
  border-radius: 3px;
  box-shadow: 5px 5px 8px #00000020, -5px -5px 8px #fff;
  cursor: pointer;
  transition: 0.5s;
}

.btn:hover {
  box-shadow: inset 5px 5px 10px rgba(160, 160, 160, 0.1),
    inset -5px -5px 10px #fff;
  background: #d0d0d0;
}
</style>
