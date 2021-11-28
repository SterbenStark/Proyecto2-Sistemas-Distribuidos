<template>
  <div class="accordion" role="tablist">
    <label>My trailers</label>
    <b-card no-body class="mb-1">
      <b-card-header header-tag="header" class="p-1" role="tab">
        <b-button block v-b-toggle.accordion-1 variant="info">Action</b-button>
      </b-card-header>
      <b-collapse id="accordion-1" visible accordion="my-accordion" role="tabpanel">
        <b-card-body>
          <ul>
            <li v-for="(obj, index) in accion" :key="index" @click="sendMovie(obj.id)"><b-link>{{obj.link}}</b-link></li>
          </ul>
        </b-card-body>
      </b-collapse>
    </b-card>

    <b-card no-body class="mb-1">
      <b-card-header header-tag="header" class="p-1" role="tab">
        <b-button block v-b-toggle.accordion-2 variant="info">Terror</b-button>
      </b-card-header>
      <b-collapse id="accordion-2" accordion="my-accordion" role="tabpanel">
        <b-card-body>
          <ul>
            <li v-for="(obj, index) in terror" :key="index" @click="sendMovie(obj.id)"><b-link>{{obj.link}}</b-link></li>
          </ul>
        </b-card-body>
      </b-collapse>
    </b-card>

    <b-card no-body class="mb-1">
      <b-card-header header-tag="header" class="p-1" role="tab">
        <b-button block v-b-toggle.accordion-3 variant="info">Drama</b-button>
      </b-card-header>
      <b-collapse id="accordion-3" accordion="my-accordion" role="tabpanel">
        <b-card-body>
          <ul>
            <li v-for="(obj, index) in drama" :key="index" @click="sendMovie(obj.id)"><b-link>{{obj.link}}</b-link></li>
          </ul>
        </b-card-body>
      </b-collapse>
    </b-card>
  </div>
</template>

<script>

export default {
  name: 'Home',
  data() {
      return {
        accion:[{link:'pelicula 1', id:1},
        {link:'pelicula 2', id:2},
        {link:'pelicula 3', id:3}],
        terror:[{link:'pelicula 1', id:1},
        {link:'pelicula 2', id:2},
        {link:'pelicula 3', id:3},
        {link:'pelicula 4', id:4}],
        drama:[{link:'pelicula 1', id:1},
        {link:'pelicula 2', id:2}]
        
      }
    },
    methods:{
      sendMovie(id){
        this.$router.push({ name: 'Pelicula', params: { id: id } })
      }
    }
    
}
</script>
