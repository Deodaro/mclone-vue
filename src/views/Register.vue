<template>
  <div class="auth-page">
    <div class="container page">
      <div class="row">
        <div class="col-md-6 offset-md-3 col-xs-12">
          <h1 class="text-xs-center">Sign Up</h1>
          <p class="text-xs-center">
            <!-- login - это тот name, который описан для страницы логина = алиас для страницы логина -->
            <router-link :to="{name: 'login'}">Need an account?</router-link>
          </p>
          <!-- VALIDATION ERRORS -->
          <!-- VALIDATION ERRORS END -->
          <form @submit.prevent="onSubmit">
            <fieldset class="form-group">
              <input
                type="text"
                class="form-control form-control-lg"
                placeholder="Username"
              />
            </fieldset>
            <fieldset class="form-group">
              <input
                type="text"
                class="form-control form-control-lg"
                placeholder="Email"
              />
            </fieldset>
            <fieldset class="form-group">
              <input
                type="password"
                class="form-control form-control-lg"
                placeholder="Password"
              />
            </fieldset>
            <button class="btn btn-lg btn-primary pull-xs-right">
              Sign Up
            </button>
          </form>
          <button @click="increaseCounter">Increase counter</button>
          {{ count }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// экспортируем пустой объект
export default {
  // задаём внутри name - это будет название нашего компонента
  // название лучше задавать такое, чтобы было понятно:
  // это компонет нашего проекта или компонент сторонней библиотеки?
  // хорошей практикой считается делать префиксы по названию проекта
  name: 'MclRegitster',
  computed: {
    count() {
      return this.$store.state.count
    }
  },
  methods: {
    onSubmit() {
      console.log('submitted form')
    },
    increaseCounter() {
      console.log('increase counter')
      this.$store.commit('increment')
    }
  }
}
</script>
