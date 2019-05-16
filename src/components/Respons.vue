<template>
  <div>123 {{props}}</div>
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
    props: ['label'],
    methods: {
      nextSecondStep(){
        this.firstStep = false
        this.secondStep = true

      }
    }
  }

</script>
