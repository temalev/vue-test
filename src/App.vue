<template>
  <div id="app">
    <div class="tableContainer">
      <div @click="isModal = true" class="button">Добавить</div>
      <!-- <table :arrStaff="arrStaff" /> -->
      <theTable :arrStaff="arrStaff" />
    </div>
    <theModal
      v-if="isModal"
      @isModal="isModal = false"
      @save="save"
      :arrStaff="arrStaff" />
  </div>
</template>

<script>
import theTable from './components/theTable/app.vue'
import theModal from './components/theModal.vue'
import { uuid } from 'vue-uuid'

export default {
  name: 'App',
  components: {
    theTable,
    theModal
  },
  data () {
    return {
      isModal: false,
      arrStaff: [
        {
          uuid: uuid.v4(),
          name: 'Зина',
          tel: '789105056044',
          chief: null
        },
        {
          uuid: uuid.v4(),
          name: 'Петр',
          tel: '789105054044',
          chief: null
        },
        {
          uuid: uuid.v4(),
          name: 'Семен',
          tel: '789105056043',
          chief: null
        }
      ]
    }
  },
  mounted () {
    if (localStorage.arrStaff) {
      this.arrStaff = JSON.parse(localStorage.arrStaff)
    }
  },
  methods: {
    save (addStaff) {
      addStaff.uuid = uuid.v4()
      this.isModal = false

      this.arrStaff.find(el => el.uuid === addStaff.chief).subordinate = addStaff

      console.log(this.arrStaff.find(el => el.uuid === addStaff.chief))

      // if (!this.arrStaff.find(el => el.uuid === addStaff.chief).length) {
      //   this.arrStaff.push(addStaff)
      // }

      localStorage.setItem('arrStaff', JSON.stringify(this.arrStaff))

      console.log(this.arrStaff)
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
  position: relative;
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
