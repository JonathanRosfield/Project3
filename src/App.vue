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
  </div>
</template>


