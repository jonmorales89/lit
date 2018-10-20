<template>
    <div class="request_item">
        <b-collapse class="request_item_card card" :open.sync="isOpen">
            <div slot="trigger" class="card-header">
                <div class="card-header-title">
                    {{ title ? title : 'Title' }} <span class="qty">Qty: {{ qty ? qty : 0 }}</span>
                </div>
            </div>
            <div class="card-content">
                <div class="content">
                    <b-field grouped>
                        <b-field label="Title" expanded>
                            <b-input v-model="title"/>
                        </b-field>
                        <b-field label="Qty">
                            <input v-model="qty" class="input" type="number"/>
                        </b-field>
                    </b-field>
                </div>
            </div>
            <footer class="card-footer">
                <a class="card-footer-item" @click="isOpen = !isOpen">Save</a>
                <a class="card-footer-item" @click="clear">Clear</a>
            </footer>
        </b-collapse>

        <div v-if="title || qty" class="request_item_add">
            <a class="button is-primary is-outlined">Add</a>
        </div>
    </div>
</template>

<script>
export default {
  name: "RequestItem",

  data: () => ({
    isOpen: true,

    title: "",

    qty: 0
  }),

  methods: {
    clear() {
      this.title = "";
      this.qty = 0;
      this.isOpen = false;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.request_item {

    &_card {
        margin-bottom: 1rem;
    }

    &_add {
        text-align: right;
    }
}

.qty {
  position: absolute;
  right: 1rem;
}
</style>
