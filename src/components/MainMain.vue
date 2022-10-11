<template>
  <div>
    <MainHeader :music="music" @genre="saveGenre" @author="saveAuthor" />
    <MainCard :inputSearch="inputSearch" :selectAuthor="selectAuthor" :music="music" />
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
      inputSearch: '',
      selectAuthor: ''
    }
  },

  methods: {
    saveGenre ( data ) {
      this.inputSearch = data;
    },

    saveAuthor ( data ) {
      this.selectAuthor = data;
    }
  },

  created () {
    axios.get( 'https://flynn.boolean.careers/exercises/api/array/music' )
      .then( r => this.music = r.data.response );
  }
}
</script>
