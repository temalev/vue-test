<template>
<div class="mainContainer">
  <div class="header">
    <div class="headerLeftColumn">Имя</div>
    <div class="headerRightColumn">Телефон</div>
  </div>

  <div class="body">
    <div v-for="(man, idMan) in arrStaff" :key="idMan" class="rowContainer">
        <row :man="man" />
        <row-tree :man="man.subordinate" />
    </div>
  </div>
</div>
</template>

<script>
import row from './row.vue'
import RowTree from './rowTree.vue'
export default {
  components: { row, RowTree },
  name: 'Table',

  props: {
    arrStaff: {
      type: Array,
      default: () => []
    }
  }
}
</script>

<style scoped>

.mainContainer{
    width: 700px;
    /* border: 1px solid rgb(198, 198, 198);
    border-radius: 5px; */
}

.header{
    display: flex;
    font-size: 20px;
    box-shadow: 0px 5px 5px rgba(228, 228, 228, 0.277);
}

.headerLeftColumn{
    display: flex;
    justify-content: center;
    align-items: center;
    border-right: 1px solid rgb(198, 198, 198);
    border-left: 1px solid rgb(198, 198, 198);
    border-top: 1px solid rgb(198, 198, 198);
    width: 300px;
    padding: 10px 0;
}

.headerRightColumn{
    display: flex;
    justify-content: center;
    align-items: center;
    width: 400px;
    padding: 10px 0;
    border-top: 1px solid rgb(198, 198, 198);
    border-right: 1px solid rgb(198, 198, 198);
}
</style>
