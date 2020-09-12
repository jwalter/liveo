<template>
  <h2>{{ msg }}</h2>
  <Competition :id="18125" />
  <table>
    <tr v-for="(competition) in competitions" :key="competition.id">
      <td>{{competition.name}}, {{competition.id}} </td>
    </tr>
  </table>
</template>

<script>
import Competition from './Competition.vue'

export default {
  name: 'CompetitionList',
  props: {
    msg: String
  },
  components: {
    Competition
  },
  data() {
    return {
      count: 0,
      competitions: [],
      currentCompId: 18125
    }
  },
  created() {
    this.fetchData();
  },
  methods: {
    fetchData() {
    var self = this;
    fetch("/api?method=getcompetitions")
      .then(response => response.json())
      .then(data => self.competitions = data.competitions.filter(c => c.date === "2020-09-12"));

    }
  }
}
</script>
