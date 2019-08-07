<template>
    <div>
      <app-data></app-data>
      <h3>COMPONENT - Table of Data</h3>
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
        <tr v-for="item in query">
          <td >{{ item.sender }}</td>
          <td>{{ item.senderCity }}</td>
          <td>{{ item.senderPostalCode }}</td>
          <td>{{ item.destinationCustoms }}</td>
          <td>{{ item.destinationCity }}</td>
          <td>{{ item.destination }}</td>
          <td>{{ item.adr }}</td>
          <td>{{ item.truckType }}</td>
          <td>{{ item.customer }}</td>
          <td>{{ item.customerPrice }}</td>
          <td>{{ item.carrier }}</td>
          <td>{{ item.carrierPrice }}</td>
          <td>{{ item.comments }}</td>
          <td>{{ item.monthAndYearOfQuery }}</td>
        </tr>
      </table>
    </div>
</template>

<script>
  import AddData from './AddData.vue';
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
    },
    created(){
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
        
    },
    components: {
      'app-data': AddData
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
