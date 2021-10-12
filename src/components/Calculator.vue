<template>
  <div class="body">
    <div class="container">
      <div class="display">
        <!-- <input type="text" placeholder="{{calVal || 0}}" /> -->
        {{ calVal || 0 }}
      </div>

      <div class="btns" v-for="item in calculatorButtonVal" :key="item">
        <button class="btn">{{ item }}</button>
      </div>

      <!-- <div class="btns">
        <div class="row">
          <button class="btn">CE</button>
          <button class="btn">x!</button>
          <button class="btn">(</button>
          <button class="btn">)</button>
          <button class="btn">%</button>
          <button class="btn">AC</button>
        </div>

        <div class="row">
          <button class="btn">sin</button>
          <button class="btn">ℼ</button>
          <button class="btn">7</button>
          <button class="btn">8</button>
          <button class="btn">9</button>
          <button class="btn">/</button>
        </div>

        <div class="row">
          <button class="btn">cos</button>
          <button class="btn">log</button>
          <button class="btn">4</button>
          <button class="btn">5</button>
          <button class="btn">6</button>
          <button class="btn">*</button>
        </div>

        <div class="row">
          <button class="btn">tan</button>
          <button class="btn">√</button>
          <button class="btn">1</button>
          <button class="btn">2</button>
          <button class="btn">3</button>
          <button class="btn">-</button>
        </div>

        <div class="row">
          <button class="btn">e</button>
          <button class="btn">x^n</button>
          <button class="btn">0</button>
          <button class="btn">.</button>
          <button class="btn">=</button>
          <button class="btn">+</button>
        </div>
      </div> -->
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
        "x^n",
        0,
        ".",
        "=",
        "+",
      ],
    };
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
  max-height: 300px;
  padding: 15px;
  border-radius: 5px;
  background: #f0f0f0;
  box-shadow: 6px 6px 10px gainsboro, -6px -6px 10px gainsboro;
}

.display {
  display: flex;
  align-items: center;
  justify-content: flex-end;
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
  width: 97%;
  margin-top: 25px;
  border: 1px solid red;
  display: flex;
  flex-direction: row;
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
}
</style>
