eslint-disable
<template>
  <div class="calculator">
    <div class="display">{{current || '0'}}</div>
    <div @click="clear" class='btn'>C</div>
    <div @click="sign" class='btn'>+/-</div>
    <div @click="percent" class='btn'>%</div>
    <div class='btn operator'>+</div>
    <div class='btn'>7</div>
    <div class='btn'>8</div>
    <div class='btn'>9</div>
    <div class='btn operator'>x</div>
    <div class='btn'>4</div>
    <div class='btn'>5</div>
    <div class='btn'>6</div>
    <div class='btn operator'>-</div>
    <div class='btn'>1</div>
    <div class='btn'>2</div>
    <div class='btn'>3</div>
    <div class='btn operator'>+</div>
    <div class='btn zero'>0</div>
    <div class='btn'>.</div>
    <div class='btn operator'>=</div>
  </div>
</template>

<script>
/* eslint-disable */

  export default{
    data() {
      return {
        current: ''
      }
    },
    methods: {
      clear() {
        this.current = '';
      },
      sign() {
        this.current = this.current.charAt(0) === '-' ? this.current.slice(1) : `-${this.current}`
      },
      percent() {
        this.current = `${parseFloat(this.current) / 100}`
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="stylus">
.calculator
  font-size 20px
  display: grid
  grid-templete-columns: repeat(4, 1fr)
  grid-grid-auto-rows: minmax(50px, auto)
  margin 0 auto
  width 400px
.display
  grid-column 1 / 5;
  background-color #333;
  color white
.zero
  grid-column 1 / 3;
.btn
  background-color #eee
  border 1px solid #333
.operator
  color #000
  background-color orange

</style>
