<template>
<div class="main">
    <div class="header">
        <span class="title">Добавление пользователя</span>
        <div class="btnClose" @click="$emit('isModal')">&times;</div>
    </div>
    <form action="">
        <div class="bodyForm">
            <div class="inputRow">
            <span class="titleInput">Имя</span>
            <input v-model="addStaff.name" type="text">
        </div>
        <div class="inputRow">
            <span class="titleInput">Телефон</span>
            <input v-model="addStaff.tel" maxlength="12" type="tel">
        </div>
        <div class="inputRow">
            <span class="titleInput">Начальник</span>
            <div class="chiefSelect">
                <span class="selectedChief">нет</span>
                <div class="btnOpenList">^</div>
            </div>
            <div class="listContainer"></div>
        </div>
        </div>
        <div class="btnSave" @click="$emit('save', addStaff)">Сохранить</div>
    </form>

</div>
</template>
<script>
export default {
  name: 'Modal',
  data () {
    return {
      addStaff: {
        name: null,
        tel: null
      }
    }
  }
}
</script>
<style scoped>
.main{
    position: absolute;
    margin: 0;
    top: 50%;
    left: 50%;
    margin-right: -50%;
    transform: translate(-50%, 0%);
    z-index: 2;
    display: flex;
    flex-direction: column;
    gap: 20px;
    width: 500px;
    height: 280px;
    background-color: #fff;
    border: 1px solid rgb(218, 218, 218);
    border-radius: 5px;
    box-shadow: 0 4px 15px rgba(165, 165, 165, 0.513);
}
.header{
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 10px 0;
}
.btnClose{
    position: absolute;
    top: 0;
    right: 10px;
    font-size: 25px;
    cursor: pointer;
    opacity: .5;
    transition: .2s;
}
.btnClose:hover{
    opacity: 1;
}
form{
    width: 80%;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    gap: 20px;
    align-items: flex-start;
}
.bodyForm{
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 20px;
    align-items: flex-start;
    justify-content: center;
}
.btnSave{
    width: 150px;
    border: 1px solid #208e2b;
    border-radius: 32px;
    cursor: pointer;
    transition: .2s;
    padding: 5px 0;
}
.btnSave:hover {
    background-color: #208e2b;
    color: #fafafa;
}
.inputRow{
    display: flex;
    width: 100%;
    justify-content: space-between;
    align-items: center;
}
input{
    width: 270px;
    height: 20px;
    border: 1px solid rgb(218, 218, 218);
    border-radius: 5px;
    padding: 5px;
    outline: none;
    transition: .2s;
}
input:focus{
    border: 1px solid rgb(112, 112, 112);
}
.chiefSelect{
    width: 282px;
    height: 35px;
    border: 1px solid rgb(218, 218, 218);
    border-radius: 5px;
    padding: 0px 10px;
    box-sizing:border-box;
    outline: none;
    transition: .2s;
    display: flex;
    justify-content: space-between;
    align-items: center;
    transition: .2s;
    cursor: pointer;
}
.chiefSelect:hover{
    border: 1px solid rgb(112, 112, 112);
}
.btnOpenList {
    transform: scaleY(0.6) rotate(180deg);
    font-size: 25px;
    height: 25px;
    width: 25px;
    flex-shrink: 0;
    opacity: .5;
}
</style>
