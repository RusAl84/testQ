<template>
  <q-page>
    <h1>Home</h1>

    <q-input v-model="text" label="Standard" />
    <q-btn color="blue"  icon-right="send" label="Отправить" @click="send" />
<!--    {{text}}-->
    <q-table
        title="Treats"
        :rows="rows"
        :columns="columns"
        row-key="name"
    />


  </q-page>
</template>

<script>
// @ is an alias to /src
import api from "@/api/api"

export default {
  name: 'Home',
  // components: {
  //   HelloWorld
  // }
  data: () => {

    return {
      text: '',


    }
  },
  methods: {
    async send() {
      var mas = await api.sendMessage(this.text)
      console.log(mas[0])
      // console.log("dssdds")
      alert(mas)
    }
  }
}
</script>
