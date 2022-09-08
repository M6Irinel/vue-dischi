<template>
  <div>
    <MainHeader @search="saveSearch" />
    <MainCard :inputSearch="inputSearch" :music="music" />
  </div>
</template>

<script>
import axios from 'axios';
import MainCard from './MainCard.vue';
import MainHeader from './MainHeader.vue';

export default {
  name: 'MainMain',
  components: {
    MainCard,
    MainHeader
  },
  data () {
    return {
      music: [],
      inputSearch: ''
    }
  },
  methods: {
    saveSearch ( data ) {
      this.inputSearch = data;
    }
  },
  created () {
    axios.get( 'https://flynn.boolean.careers/exercises/api/array/music' )
      .then( r => this.music = r.data.response );
  }
}
</script>
