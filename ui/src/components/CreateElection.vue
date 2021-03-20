<template>
  <div class='create-election'>
    <h2>Create Election</h2>
    <div class='election-input'>
      <label for='election-name'>Election Name: </label>
      <input type='text' id='election-name' v-model='electionName'>
    </div>
    <div class='election-input'>
      <label for='election-candidates'>Election Candidates: </label>
      <textarea id='election-candidates' v-model='electionCandidates'>
      </textarea>
    </div>
    <div class='election-input'>
      <button @click='createElection'>Submit</button>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

function separateCandidateNames(electionCandidates) {
  const candidates = electionCandidates.split(',').map(function(candidateName) {
    return candidateName.trim();
  });
  return candidates;
}

export default {
  name: 'CreateElection',
  data: function() {
    return {
      WEB_SERVICE: (this.$config.WEB_SERVICE_ROOT + 'election'),
      electionName: '',
      electionCandidates: '',
    };
  },
  methods: {
    createElection() {
      const candidates = separateCandidateNames(this.electionCandidates);
      axios({
        method: 'post',
        url: this.WEB_SERVICE,
        data: {
          electionName: this.electionName,
          electionCandidates: candidates,
        }
      });
    },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

div {
  padding: 1em;
}

textarea {
  display: block;
}

.election-input {
  text-align: left;
}

</style>
