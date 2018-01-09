<template>
  <div>

    <p>
      Search (type min 2 characters)
      <input id="awesomplete"/>
    </p>

    <p>
      Add new <input type="text" v-model="newValue" @keyup.enter="add">
      <button @click="add">Add</button>
    </p>

    <pre v-text="$data"></pre>

  </div>
</template>

<script>
  import Awesomplete from 'awesomplete'

  export default {

    name: 'AwesompleteExample',

    data () {
      return {
        awesomplete: null,
        newValue: '',
        list: ['Bakso Solo', 'Bakso Enak', 'Sate Padang', 'Mie Aceh', 'Soto Banjar'],
      }
    },

    mounted () {
      const input = document.querySelector('#awesomplete')
      this.awesomplete = new Awesomplete(input)
      this.awesomplete.list = this.list
    },

    methods: {
      add () {
        this.list.push(this.newValue)
        this.newValue = ''
      },
    },

  }
</script>
