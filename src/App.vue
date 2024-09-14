<template>
  <div id="app">
    <h1>Create your Contact List!</h1>

    <section id="contact-form">
      <h2>Add a New Contact</h2>
      <form @submit.prevent="addContact">
        <label for="contactName">Name:</label>
        <input v-model="newContactName" type="text" id="contactName" required />

        <label for="contactPhone">Phone Number:</label>
        <input v-model="newContactPhone" type="tel" id="contactPhone" required />

        <button type="submit">Add Contact</button>
      </form>
    </section>

    <section id="contact-list">
      <h2>Contact List</h2>
       <ul id="contactList">
         <li v-for="(contact, index) in contacts" :key="index">
          {{ contact.name }}: {{ contact.phone }}
         </li>

       </ul>
    </section>
  </div>
</template>

<script>
 import "./style.css";;
export default {
  data() {
    return {
      newContactName: '',
      newContactPhone: '',
      contacts: []
    };
  },
  methods: {
    addContact() {
      if (this.newContactName && this.newContactPhone) {
        this.contacts.push({
          name: this.newContactName,
          phone: this.newContactPhone
        });
        this.newContactName = '';
        this.newContactPhone = '';
      }
    }
  }
};
</script>


