<template>
  <div>
    <div>
      <div class="container text-center">
        <h1>Real news, curated by real humans</h1>
        <p>
          Packed with the trends, news & links you needs to be smart, informed,
          and ahead of the curve.
        </p>
        <div>
          <div class="container">
            <div class="row">
              <div class="col-md-3 d-flex" v-for="New in News" :key="New.id">
                <b-card
                  :title="New.title"
                  :img-src="New.image"
                  img-alt="Image"
                  img-top
                  tag="article"
                  style="max-width: 18rem;"
                  class="mt-2 border-0 card-news"
                >
                  <b-card-text>{{ New.description }}</b-card-text>
                  <b-button href="#" variant="btn btn-outline-info">
                    Subscribe
                    <i class="far fa-envelope"></i> >>>
                  </b-button>
                </b-card>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="container text-center mt-4">
        <h1>Up-and-coming</h1>
        <p>
          If these newsletters reach their goals (or get a sponsorship), we'll
          bring on expert writers and launch them. Vote for all your favorites:
        </p>
        <div>
          <div class="container">
            <div class="row">
              <div class="col-md-3 d-flex" v-for="New in News" :key="New.id">
                <b-card
                  :title="New.title"
                  :img-src="New.image"
                  img-alt="Image"
                  img-top
                  tag="article"
                  style="max-width: 18rem;"
                  class="mt-2 border-0 card-news"
                >
                  <b-card-text>{{ New.description }}</b-card-text>
                  <b-button href="#" variant="btn btn-outline-info">
                    Subscribe
                    <i class="far fa-envelope"></i> >>>
                  </b-button>
                </b-card>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Axios from 'axios'
export default {
  data() {
    return {
      News: []
    }
  },
  created() {
    this.getUrl()
  },
  methods: {
    getUrl() {
      const urlNews = process.env.API_URL + 'newsletters'
      Axios.get(urlNews)
        .then((response) => {
          this.News = response.data
          this.getfuncion(response.data)
        })
        .catch(() => {})
    },
    getfuncion(voletines) {
      const voleta = voletines.filter(function(voletin) {
        return voleta.target >= voleta.subscribed
      })
    }
  }
}
</script>

<style>
.card-news img {
  width: 5rem;
  height: 5rem;
  border-radius: 100%;
  margin-left: 5rem;
}
text-orange {
  color: orangered;
}
</style>
