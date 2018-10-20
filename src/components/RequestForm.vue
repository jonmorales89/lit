<template>
    <div>
        <div class="hero is-primary">
            <div class="hero-body">
                <h1 class="title">Literature Manager</h1>
            </div>
        </div>

        <section class="request_form">
            <b-field grouped>
                <b-field label="Congregation">
                    <b-select placeholder="select a congregation">
                        <option v-for="option in congregations"
                                :value="option.id"
                                :key="option.id">
                            {{ option.title }}
                        </option>
                    </b-select>
                </b-field>

                <b-field label="Group Overseer">
                    <b-select placeholder="select an overseer">
                        <option v-for="option in overseers"
                                :value="option.id"
                                :key="option.id">
                            {{ option.title }}
                        </option>
                    </b-select>
                </b-field>

                <b-field label="Name" expanded>
                    <b-input />
                </b-field>
            </b-field>


            <b-field label="Email" expanded>
                <b-input type="email"/>
            </b-field>

            <hr>

            <request-item />

            <hr>

            <div class="request_form_action is-pulled-right">
                <a class="button is-primary is-outlined">Reset</a>
                <a class="button is-primary is-outlined">Submit</a>
            </div>

        </section>
    </div>
</template>

<script>
import RequestItem from "./RequestItem";
export default {
  name: "RequestForm",

  components: { RequestItem },

  data: () => ({
    congregations: [
      {
        title: "Rowland Heights",
        id: 1
      },
      {
        title: "Nogales",
        id: 2
      },
      {
        title: "Walnut",
        id: 3
      },
      {
        title: "Rowland Chinese",
        id: 4
      }
    ],

    overseers: [
      {
        title: "Moreno",
        id: 1
      },
      {
        title: "Sheih",
        id: 2
      },
      {
        title: "Hines",
        id: 3
      }
    ]
  })
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.request_form {
  margin-top: 2rem;
  margin-left: 1.5rem;
  margin-right: 1.5rem;

  &_action > a{
    margin-left: 1rem;
  }
}
</style>
