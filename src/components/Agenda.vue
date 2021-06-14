<template>
  <div class="container agenda">
    <div class="row">
      <div class="col-xs-12 col-sm-12 col-md-12 col-lg-12 center-xs">
        <h1>Agenda</h1>
      </div>
    </div>
    <div class="row center-xs mt-40">
      <div class="col-xs-12 col-sm-12 col-md-8 col-lg-5">
        <div class="input-group flex-nowrap">
          <span class="input-group-text" id="addon-wrapping"></span>
          <input type="text" v-model="this.contact.name" class="form-control" placeholder="Name" />
        </div>
      </div>
    </div>
    <div class="row center-xs mt-40">
      <div class="col-xs-12 col-sm-12 col-md-8 col-lg-5">
        <div class="input-group flex-nowrap">
          <span class="input-group-text" id="addon-wrapping"></span>
          <input type="text" v-model="this.contact.phone" class="form-control" placeholder="Phone" />
        </div>
      </div>
    </div>
    <div class="row center-xs mt-40">
      <div class="col-xs-12 col-sm-12 col-md-12 col-lg-12">
        <button type="button" class="btn btn-primary" @click="createContact()">{{ !edit ? 'Add Contact' : 'Finish Edit' }}</button>
      </div>
    </div>
    <div class="row center-xs mt-40">
      <div class="col-xs-12 col-sm-12 col-md-8 col-lg-5">
        <ul class="list-group start-xs">
          <li class="list-group-item row beetwen-xs" v-for="(item, index) in contacts" :key="item">
            <p>{{ item.name }} - {{ item.phone }}</p>
            <button type="button" class="btn btn-warning" style="margin-top: 5px;" @click="editContact(index)">Edit</button>
            <button type="button" class="btn btn-danger" style="margin-top: 5px;" @click="deleteContact(index)">Delete</button>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Agenda',
  data() {
    return {
      contact: {
        name: '',
        phone: '',
      },
      edit: false,
      contacts: [{ name: 'Luis Carrillo', phone: '8711001907' }],
    };
  },
  methods: {
    createContact(idx) {
      const newContact = { ...this.contact };
      
      if(!this.edit){
        this.contacts.push(newContact);
      }else{
        this.contacts[idx] = newContact;
        this.edit = false;
      }

      this.contact = { name: '', phone: '' };
    },
    editContact(idx) {
      this.contact = this.contacts[idx];
      this.edit = true;
    },
    deleteContact(idx) {
      this.contacts.splice(idx, 1);
      this.contact = { name: '', phone: '' };
    },
  },
};
</script>
<style></style>
