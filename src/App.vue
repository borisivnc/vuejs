<template>
  <div>
    <div>
      <h1>Participants list</h1>
      <ol>
      	<li v-for="p in participants">{{p.firstname}} {{p.lastname}}</li>
      </ol>
    </div>
    
    

    <h3>New participant</h3>
    <new-participant-form @added="addNewParticipant($event)"></new-participant-form>
  </div>
</template>

<script>
	import NewParticipantForm from "./NewParticipantForm.vue";

  export default {
  
    components: {NewParticipantForm},
    
    data() {
      return {
      	
      		participants: [
      		{ firstname : 'John', lastname: 'Doe' },
      		{ firstname : 'Robin', lastname: 'Hood' },
      		{ firstname : 'Chuck', lastname: 'Norris' },
      		]
      
      };
    },
    methods: {
      addNewParticipant(participant) {
      	
      		this.participants.push( { firstname : participant.firstname, lastname: participant.lastname } );
      		
      }
    }
  };
</script>
