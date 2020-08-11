<template>
  <div>
    <input type="text" v-model="newContact" placeholder="Name" />
    <button @click="addContact">Add</button>
    <button @click="sortContacts">Sort</button>

    <transition-group name="slide-up" tag="ul" appear="">
      <li class="contact" v-for="contact in contacts" :key="contact">
        {{ contact }}
      </li>
    </transition-group>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newContact: '',
      contacts: ['Beau Thabeast', 'Cindy Rella', 'Alice Vunderlind']
    }
  },
  methods: {
    addContact() {
      this.contacts.push(this.newContact)
      this.newContact = ''
    },
    sortContacts() {
      this.contacts.sort()
    }
  }
}
</script>

<style scoped>
.contact {
  list-style: none;
}
</style>
