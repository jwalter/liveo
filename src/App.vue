<template>
  <CompetitionList msg="Dagens tävlingar"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import CompetitionList from './components/CompetitionList.vue'
import Competition from './components/Competition.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    CompetitionList,
    Competition
  }
}
</script>
