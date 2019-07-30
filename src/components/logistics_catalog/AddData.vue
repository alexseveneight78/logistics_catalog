<template>
  <div>
    <h3>Add Data Template</h3>
    <table>
      <tr>
        <td>Страна отправления</td>
        <td>Город</td>
        <td>Почтовый код</td>
        <td>Таможня назначения</td>
        <td>Город назначения</td>
        <td>Страна назначения</td>
        <td>АДР</td>
        <td>Тип машины</td>
        <td>Клиент</td>
        <td>Цена клиента</td>
        <td>Перевозчик</td>
        <td>Цена перевозчика</td>
        <td>Комментарий</td>
        <td>Месяц и год запроса</td>
      </tr>
      <tr>
        <td><input type="text"></td>
        <td><input type="text"></td>
        <td><input type="text"></td>
        <td><input type="text"></td>
        <td><input type="text"></td>
        <td><input type="text"></td>
        <td><input type="text"></td>
        <td><input type="text"></td>
        <td><input type="text"></td>
        <td><input type="text"></td>
        <td><input type="text"></td>
        <td><input type="text"></td>
        <td><input type="text"></td>
        <td><input type="text"></td>
      </tr>
    </table>
    <button @click="">Add Data to Data Table</button>
  </div>
</template>

<script>
  export default {

  }
</script>

<style scoped>
  div {
    box-shadow: 2px 3px 3px #ccc;
    outline: 1px solid #ccc;
    background-color: #cccfff;
    margin: 20px 0;
  }
  table {
    border: 1px solid #000;
    font-size: 14px;
  }
  table tr {
    outline: 1px solid red;
    display: flex;
    justify-content: flex-start;
    flex-wrap: nowrap;
  }
  table tr td {
    outline: 1px dashed #ccc;
    text-align: center;
    width: 10em;
  }
  table tr input {
    width: 10em;
  }
</style>
