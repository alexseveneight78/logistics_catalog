<template>
    <div>
      <h3>Table of Data</h3>
      <button @click="fetchData">Fill Table</button>
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
          <td v-for="item in query">{{ item.sender }}</td>
        </tr>
      </table>
    </div>
</template>

<script>
    export default {
      props: ['query'],
      methods: {
      fetchData(){
        this.$http.get('https://logisticscatalog.firebaseio.com/data.json')
          .then(response => {
            return response.json();
          })
          .then(data => {
            const resultArray = [];
            for(let key in data){
              resultArray.push(data[key])
            }
            this.query = resultArray;
          })
      }
      }
    }
</script>

<style scoped>
  div {
    overflow: visible;  
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
