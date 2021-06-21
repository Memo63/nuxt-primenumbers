<template>
  <div class="container">
    <div>
      <Logo />
      <h1 class="title">
        primzahlen
      </h1>
      <form class="max-w-xs border-2 border-bg-gray-500">
        <h2 class="text-xl my-5">
          Prime numbers
        </h2>
        <div class="md:flex md:items-center mb-6">
          <label class="block text-gray-500 font-bold md:text-right mb-1 md:mb-0 pr-4">
            Number:
          </label>
          <input
            v-model="number"
            class="bg-gray-200 appearance-none border-2 border-gray-200 rounded w-full py-2 px-4 text-gray-700 leading-tight focus:outline-none focus:bg-white focus:border-purple-500"
            type="number"
          >
        </div>
        <div
          v-if="number>1"
        >
          Primzahlen: {{ getNumbers2 }}
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      primeNumbers: [],
      number: Number
    }
  },
  computed: {
    getNumbers2 () {
      let isPrime = true
      const pnumbers = []

      for (let i = this.number; i > 1; i--) {
        for (let j = 2; j < i; j++) {
          if (i % j === 0) {
            isPrime = false
            break
          }
        }
        if (isPrime) {
          pnumbers.push(i)
        }
        isPrime = true
      }
      return pnumbers
    }

  }

}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
