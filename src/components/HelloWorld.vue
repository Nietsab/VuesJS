<template>
  <div class="hello">
    <h1>{{ msg }}</h1>

    <div name="txt">
      <input type="text" name= "input" v-model="message" v-on:keyup.enter="submit">
      <p onkeyup="errormessage">{{ taille }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String ,
    taille: String
  },
  data() {
    return  {
      message: "",
      errormessage: ""
    };
  },
  methods: {
    submit(){
      this.msg = this.message
      this.errormessage = (this.msg.length > 5) ? ' ' : '5 caractères min '
      this.errormessage += (this.msg.match(/[A-Z]+/))? ' ' : ' - Au moins 1 majuscule  '
      this.errormessage += (this.msg.match(/[\d]+/))? ' ' : '- Au moins 1 chiffre '
      this.taille = this.errormessage
    }
  }
}
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
