<template>
  <div>
    <form action="">
      <div class="container">
        <div class="form-group purple-border">
          <textarea class="form-control" v-model="newquotevalue"></textarea>
        </div>
        <button @click.prevent="CreateNew" class="btn btn-success">
          Add Quote
        </button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newquotevalue: "",
    };
  },

  methods: {
    CreateNew() {
      if(this.newquotevalue != ""){
         this.$emit("quoteadded", this.newquotevalue);
      this.newquotevalue = "";
      }
      
    },
  },
};
</script>

<style>
.purple-border textarea {
  border: 1px solid #ba68c8;
  height: 200px;
  width: 600px;
}
.purple-border .form-control:focus {
  border: 1px solid #ba68c8;
  box-shadow: 0 0 0 0.2rem rgba(186, 104, 200, 0.25);
}

.green-border-focus .form-control:focus {
  border: 1px solid #8bc34a;
  box-shadow: 0 0 0 0.2rem rgba(139, 195, 74, 0.25);
}
</style>