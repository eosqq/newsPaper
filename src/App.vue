<template>
  <div class="container">
    <div class="card center">
      <h3>Actually news {{ date }} </h3>
      <span>Кол-во открытий: {{ openRate }} | Прочитано: {{ readRate }} </span>
    </div>
    <app-news
      v-for="item in news"
      :key="item.id"
      :title="item.title"
      :id="item.id"
      :was-read="item.wasRead"
      :is-open="isOpen"
      @open-news="openNews"
      @read-news="readNews"
    ></app-news>
  </div>
</template>

<script>

import AppNewsVue from './components/AppNews.vue'

export default {
  data () {
    return {
      date: new Date().toLocaleDateString(),
      news: [
        { title: 'news 1', id: 1, wasRead: false },
        { title: 'news 2', id: 2, wasRead: false },
        { title: 'news 3', id: 3, wasRead: false },
        { title: 'news 4', id: 4, wasRead: false }
      ],
      isOpen: false,
      openRate: 0,
      readRate: 0
    }
  },

  methods: {
    openNews () {
      this.openRate++
    },

    readNews () {
      this.readRate++
    }
  },

  components: {
    'app-news': AppNewsVue
  }
}
</script>

<style>

</style>
