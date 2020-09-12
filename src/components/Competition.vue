<template>
  <h3>Selected: {{ id }}</h3>
  
</template>

<script>
export default {
  name: 'Competition',
  props: {
    id: String
  },
  data() {
    return {
      competition: {}
    }
  },
  created() {
    this.fetchData();
  },
  methods: {
    fetchData() {
    var self = this;
    fetch("/api?method=getcompetitioninfo&comp=" + this.id)
      .then(response => response.json())
      .then(data => self.competition = data);

    }
  }
}
</script>
