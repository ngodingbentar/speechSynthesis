<template>
  <div class="w-full h-full">
    <div class="card">
      <div class="text-4xl mt-8">speechSynthesis - Ngodingbentar</div>
      <div class="p-10">
        <textarea
          class="
            form-control
            block
            w-full
            px-3
            py-1.5
            text-base
            font-normal
            text-gray-700
            bg-white bg-clip-padding
            border border-solid border-gray-300
            rounded
            transition
            ease-in-out
            m-0
            focus:text-gray-700 focus:bg-white focus:border-blue-600 focus:outline-none
          "
          id="exampleFormControlTextarea1"
          rows="3"
          placeholder="Your message"
          v-model="text"
        ></textarea>
      </div>
      <div>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" @click="speak">
          Speak
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      text: 'Hello Ngodingbentar!'
    }
  },
  methods: {
    speak() {
      const msg = new SpeechSynthesisUtterance(this.text)
      window.speechSynthesis.speak(msg)
    }
  }
}
</script>

<style>
.card {
  text-align: center;
  margin: auto;
  height: 100vh;
  padding: auto;
  justify-content: center;
  justify-items: center;
}
</style>