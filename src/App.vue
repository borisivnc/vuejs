<template>
  <div>
    <div>
      <h1>Participants list</h1>
      <ol>
      	<li v-for="p in participants">{{p.firstname}} {{p.lastname}}</li>
      </ol>
    </div>
    
    

    <h3>New participant</h3>
    <form @submit.prevent="addNewParticipant()">
      <label>Firstname: </label>
      <input type="text" v-model="firstname">
      <br />
      <br />
      <label>Lastname: </label>
      <input type="text" v-model="lastname">
      <br />
      <br />
      <button>Add new participant</button>
    </form>
  </div>
</template>

<script>
  export default {
    data() {
      return {
      	
      		participants: [
      		{ firstname : 'John', lastname: 'Doe' },
      		{ firstname : 'Robin', lastname: 'Hood' },
      		{ firstname : 'Chuck', lastname: 'Norris' },
      		],
      		
      		firstname:'',
      		lastname:''
      
      };
    },
    methods: {
      addNewParticipant() {
      	
      		this.participants.push( { firstname : this.firstname, lastname: this.lastname } );
      		
      		this.firstname = '';
      		this.lastname = '';
      }
    }
  };
</script>
