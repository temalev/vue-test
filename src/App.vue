<template>
  <div id="app">
    <div class="tableContainer">
      <div class="button">Добавить</div>
      <theTable :arrStaff="arrStaff" />
    </div>

  </div>
</template>

<script>
import theTable from './components/theTable.vue'

export default {
  name: 'App',
  components: {
    theTable
  },
  data () {
    return {
      arrStaff: [
        {
          name: 'Зина',
          phoneNumber: '789105056044',
          chief: null
        },
        {
          name: 'Петр',
          phoneNumber: '789105054044',
          chief: null
        },
        {
          name: 'Семен',
          phoneNumber: '789105056043',
          chief: null
        }
      ]
    }
  }
}
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.tableContainer{
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 10px;
}
.button{
  width: 150px;
  height: 30px;
  display: flex;
  justify-content: center;
  align-items: center;
  border: 1px solid rgb(47, 47, 142);
  border-radius: 32px;
  transition: .2s;
  cursor: pointer;
}
.button:hover{
  background-color: rgb(47, 47, 142);
  color: #fafafa;
}
</style>
