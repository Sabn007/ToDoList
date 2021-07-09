import BootstrapVue from 'bootstrap-vue/dist/bootstrap-vue.esm'; import
'bootstrap-vue/dist/bootstrap-vue.css'; import
'bootstrap/dist/css/bootstrap.css'; Vue.use(BootstrapVue);
<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div id="app">
      <div class="container d-flex justify-content-center align-items-center">
        <div class="card wt-3 shadow-sm w-100">
          <div class="card-header bg-light">
            <h2>{{ name }}</h2>
          </div>
          <div class="card-body">
            <div class="input-container mt-3">
              <input
                type="text"
                name="ToDo"
                placeholder="What are you planning to do"
                class="form-control"
                @keyup.enter="add()"
                v-model="message"
              />
            </div>
            <ul class="list-group mt-3">
              <li
                class="list-group-item d-flex justify-content-between"
                v-for="(list, index) in lists"
              >
                <span class="message">
                  <span style="color: black"> {{ index + 1 }}. </span>
                  {{ list }}</span
                >
                <div class="btn-group">
                  <button
                    class="btn btn-danger"
                    type="button"
                    @click="remove(index)"
                  >
                    Delete
                  </button>
                  <button
                    class="btn btn-info"
                    type="button"
                    @click="edit(index)"
                  >
                    Edit
                  </button>
                </div>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
