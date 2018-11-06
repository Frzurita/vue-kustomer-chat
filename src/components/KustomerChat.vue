<template>
  <div class="hello">
    <h1>Basic example to integrate Kustomer chat in a component</h1>
    <button @click="initCustomerChat">start kustomer chat</button>
  </div>
</template>

<script>
setCustomerChat()
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  methods: {
    async initCustomerChat () {
      if (!Kustomer.start) await Kustomer.init('API_KEY')
      console.log('Starting the app')
      Kustomer.start()
      console.log('clearing the data')
      await Kustomer.clear()
      console.log('opening the app')
      Kustomer.open()
    }
  }
}
function setCustomerChat () {
  (function(a,b,c,d){a.Kustomer=c,c._q=[],c._i=[],c.init=function(a){function b(a,b){a[b]=function(){a._q.push([b].concat(Array.prototype.slice.call(arguments,0)))}}for(var d="init clear identify track start describe on".split(" "),e=0;e<d.length;e++)b(c,d[e]);c._i.push(a)};var e=b.createElement("script");e.type="text/javascript",e.async=!0,e.src="https://cdn.kustomerapp.com/cw/sdk.v1.1.min.js";var f=b.getElementsByTagName("script")[0];f.parentNode.insertBefore(e,f)})(window,document,window.Kustomer||{})
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
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
