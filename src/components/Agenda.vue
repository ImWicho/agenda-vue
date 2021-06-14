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
          <input type="text" class="form-control" placeholder="Name" />
        </div>
      </div>
    </div>
    <div class="row center-xs mt-40">
      <div class="col-xs-12 col-sm-12 col-md-8 col-lg-5">
        <div class="input-group flex-nowrap">
          <span class="input-group-text" id="addon-wrapping"></span>
          <input type="text" class="form-control" placeholder="Phone" />
        </div>
      </div>
    </div>
    <div class="row center-xs mt-40">
      <div class="col-xs-12 col-sm-12 col-md-12 col-lg-12">
        <button type="button" class="btn btn-primary">Add Contact</button>
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
      contacts: [],
    };
  },
  methods: {
    createContact() {},
    editContact(idx) {
      this.contact = this.contacts[idx];
    },
  },
};
</script>
<style></style>
