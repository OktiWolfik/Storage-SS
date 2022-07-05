<template>
  <v-data-table
    :headers="headers"
    :items="desserts"
    :items-per-page="5"
    class="elevation-1"
  ></v-data-table>
</template>

<script>
  export default {
    data () {
      return {
        headers: [
          {
            text: 'Наименование',
            align: 'start',
            sortable: false,
            value: 'package',
          },
          { text: 'Опция', value: 'Number' },
          { text: 'Количество', value: 'quantity' },
          { text: 'Поставщик', value: 'supplier' },
          { text: 'Сумма', value: 'total' },
          { text: 'Дата', value: 'date' },
        ],
        desserts: [
          {
            package: 'Сахар-песок',
            Number: 'поступление',
            quantity: 24,
            supplier: 'ИП Иванов',
            total: '15000 руб.',
            date: '13.06.2022'
          },
          {
            package: 'Манная крупа',
            Number: 'возврат',
            quantity: 37,
            supplier: 'Родные края',
            total: '13500 руб.',
            date: '05.07.2022'
          },
          {
            package: 'губка для кухни',
            Number: 'отгрузка',
            quantity: 23,
            supplier: 'Каждый день',
            total: '14000 руб.',
            date: '01.07.2022'
          },
        ],
      }
    },
  }
</script>
