<template>
  <div>123 {{text}}</div>
</template>
<script>

  export default {
    components: {
    },
    name: 'app',
    data () {
      return {
        firstStep: true,
        secondStep: false,
      }
    },
    methods: {
      nextSecondStep(){
        this.firstStep = false
        this.secondStep = true

      }
    }
  }

</script>
