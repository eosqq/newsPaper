<template>
    <div class="card">
        <h3> {{ title }} </h3>
        <button class="btn" @click="open"> {{ isNewOpen ? 'Закрыть' : 'Открыть' }} </button>
        <button class="btn danger" v-if="wasRead" @click="unread">Отметить непрочитанным</button>
        <div v-if="isNewOpen">
            <hr />
            <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Amet, dignissimos?</p>
            <button class="btn primary" v-if="!wasRead" @click="read">Подробнее</button>
        </div>
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
  },

  emits: ['open-news', 'read-news', 'unread-news'],

  methods: {
    open () {
      this.isNewOpen = !this.isNewOpen
      if (this.isNewOpen) {
        this.$emit('open-news')
      }
    },

    read () {
      this.isNewOpen = false
      this.$emit('read-news', this.id)
    },

    unread () {
      this.$emit('unread-news', this.id)
    }
  }
}
</script>

<style>

</style>
