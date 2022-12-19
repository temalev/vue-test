<template>
  <div class="row">
    <div class="leftColumn">{{man.name}}</div>
    <div class="rightColumn">{{man.tel}}</div>
  </div>
</template>

<script>
export default {
  name: 'Row',
  props: {
    man: {
      type: Object,
      default: () => {}
    }
  }
}
</script>

<style scoped>
.row {
    display: flex;
    border-bottom: 1px solid rgb(234, 234, 234);
}

.leftColumn {
    display: flex;
    justify-content: center;
    align-items: center;
    border-right: 1px solid rgb(198, 198, 198);
    border-left: 1px solid rgb(198, 198, 198);
    width: 300px;
    padding: 10px 0;
}

.rightColumn {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 400px;
    padding: 10px 0;
    border-right: 1px solid rgb(198, 198, 198);
}
</style>
