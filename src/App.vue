<script>
export default{
  name: 'App',
  data(){
    return{
      emails: []
    }
  },

  mounted() {
    for (let i = 0; i < 10; i++) { 
    axios
    .get('https://flynn.boolean.careers/exercises/api/random/mail')
    .then((response) => {     
      this.emails.push(response.data.response);      
    })
    }
  }
}

</script>

<template>
  
  <!-- ? Quale delle due versioni è più corretta ? -->

  <ul v-if="emails.length == 10">
    <li v-for="email in emails"><a href="#">{{ email }}</a></li> 
  </ul>

  <!-- <ul>
    <li v-if="emails.length == 10" v-for="email in emails"><a href="#">{{ email }}</a></li> 
  </ul> -->

</template>

<style>
ul{
  list-style: none;

  & a{
    color: white;
  }
}
</style>


