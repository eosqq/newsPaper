<template>
    <div class="card">
        <h3> {{ title }} </h3>
        <button class="btn" @click="isNewOpen = !isNewOpen"> {{ isNewOpen ? 'Закрыть' : 'Открыть' }} </button>
        <p v-if="isNewOpen">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Amet, dignissimos?</p>
    </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true
    },
    id: {
      type: Number,
      required: true
    },
    wasRead: {
      type: Boolean,
      required: false,
      default: false
    },
    isOpen: {
      type: Boolean,
      required: false,
      default: false
    }
  },

  data () {
    return {
      isNewOpen: this.isOpen
    }
  }
}
</script>

<style>

</style>
