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
        <td><input type="text" v-model="query.sender"></td>
        <td><input type="text" v-model="query.senderCity"></td>
        <td><input type="text" v-model.number="query.senderPostalCode"></td>
        <td><input type="text" v-model="query.destinationCustoms"></td>
        <td><input type="text" v-model="query.destinationCity"></td>
        <td><input type="text" v-model="query.destination"></td>
        <td><input type="text" v-model="query.adr"></td>
        <td><input type="text" v-model="query.truckType"></td>
        <td><input type="text" v-model="query.customer"></td>
        <td><input type="text" v-model.number="query.customerPrice"></td>
        <td><input type="text" v-model="query.carrier"></td>
        <td><input type="text" v-model.number="query.carrierPrice"></td>
        <td><textarea name="" id="" cols="15" rows="3" v-model="query.comments"></textarea></td>
        <td><input type="text" v-model="query.monthAndYearOfQuery"></td>
      </tr>
    </table>
    <button @click="submit">Add to Data Table</button>
    <button @click="fetchData">Fill Table</button>
  </div>
</template>

<script>
  export default {
    data(){
      return {
        query: {
          sender: '',
          senderCity: '',
          senderPostalCode: '',
          destinationCustoms: '',
          destinationCity: '',
          destination: '',
          adr: '',
          truckType: '',
          customer: '',
          customerPrice: '',
          carrier: '',
          carrierPrice: '',
          comments: '',
          monthAndYearOfQuery: ''
        }
      }
    },
    methods: {
      submit(){
        this.$http.post('https://logisticscatalog.firebaseio.com/data.json', this.query)
          .then(response => {
            console.log(response)
          })
      },
      fetchData(){
        this.$http.get('https://logisticscatalog.firebaseio.com/data.json')
          .then(response => {
            return response.json();
          })
          .then(data => {
            const resultArray = [];
            
          })
      }
    }
  }
</script>

<style scoped>
  div {
    width: 105%;
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
