<template>
<div>
  <h1>이벤트 클릭</h1>
  <button @click="increaseCnt(); printConsole()">Add 1</button>
  <p>The counter is : {{cnt}}</p>
</div>
<div>
  <select v-model="selectedValue" @change="changeSelect">
    <option value="1">서울</option>
    <!-- 표시되는 것과 저장값이 다르게 하고 싶으면 value사용 -->
    <option>부산</option>
    <option>제주</option>
  </select>
</div>
<div>
  {{txtVal}}
  <input type="txtVal" v-model="txtVal" 
  @keyup="changeTxtVal"
  @keyup.enter="enterTxtVal">
  <!-- @change는 포커스를 벗어나면 실행, @keyup은 적을 때마다 실행 -->
</div>
</template>

<script>
export default {
  data() {
    return {
      txtVal: '',
      selectedValue: '',
      cnt: 0
    }
  },
  methods: {
    changeTxtVal() {
      console.log(this.txtVal);
    },
    changeSelect() {
      alert(this.selectedValue);
    },
    increaseCnt() {
      this.cnt++;
    },
    printConsole() {
      console.log(this.cnt);
    }
  }
}
</script>

<style>

</style>