<template>
  <div>
    <RequestForm />
  </div>
</template>

<script>
// @ is an alias to /src
import RequestForm from "@/components/RequestForm.vue";

export default {
  name: "home",
  components: {
    RequestForm
  }
};
</script>
