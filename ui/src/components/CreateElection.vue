<template>
  <div class='create-election'>
    <h2>Create Election</h2>
    <form id='create-election' @submit='createElection'>
      <div class='election-input'>
        <label for='election-name'>Election Name: </label>
        <input type='text' id='election-name' v-model='electionName'>
      </div>
      <div class='election-input'>
        <label for='election-candidates'>Election Candidates: </label>
        <input type='textarea' id='election-candidates' v-model='electionCandidates'>
      </div>
      <div class='election-input'>
        <button type='submit'>Submit</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: 'CreateElection',
  props: {
    msg: String
  },
  data: function() {
    return {
      WEB_SERVICE_ROOT: this.$config.WEB_SERVICE_ROOT,
      electionName: '',
      electionCandidates: '',
    };
  },
  methods: {
    createElection() {
      console.log('TODO: create the election');
    },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

div {
  padding: 1em;
}

.election-input {
  text-align: left;
}

</style>
