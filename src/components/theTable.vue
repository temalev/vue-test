<template>
<div class="mainContainer">
    <div class="header">
        <div class="headerLeftColumn">Имя</div>
        <div class="headerRightColumn">Телефон</div>
    </div>
    <div class="body">
        <div v-for="man in arrStaff" :key="man" class="row">
            <div class="leftColumn">{{man.name}}</div>
            <div class="rightColumn">{{man.phoneNumber}}</div>
    </div>

    </div>
</div>
</template>
<script>
export default {
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
    border: 1px solid rgb(198, 198, 198);
    border-radius: 5px;
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
    width: 40%;
    padding: 10px 0;
}
.headerRightColumn{
    display: flex;
    justify-content: center;
    align-items: center;
    width: 60%;
    padding: 10px 0;
}
.row{
    display: flex;
    border-top: 1px solid rgb(234, 234, 234);

}
.leftColumn{
    display: flex;
    justify-content: center;
    align-items: center;
    border-right: 1px solid rgb(198, 198, 198);
    width: 40%;
    padding: 10px 0;
}
.rightColumn{
    display: flex;
    justify-content: center;
    align-items: center;
    width: 60%;
    padding: 10px 0;
}
</style>
