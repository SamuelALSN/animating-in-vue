<template>
  <div>
    <input type="text" v-model="newContact" placeholder="Name" />
    <button @click="addContact">Add Contact</button>
    <button @click="sortContact">Sort Contact</button>

    <transition-group name="slide-up" tag="ul" appear>
      <li v-for="contact in contacts" :key="contact">
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
    sortContact () {
      this.contacts.sort()
    }
  }
}
</script>
<style>
.slide-up-enter {
  transform: translateY(10px);
  opacity: 0;
}
.slide-up-enter-active {
  transition: all 0.2s ease;
}

</style>
