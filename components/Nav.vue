<template>
  <div>
    <div class="container border">
      <div class="container d-flex pt-2">
        <div>
          <h4 class="text-oranged">[INSIDE]</h4>
        </div>
        <div class="container d-flex justify-content-end pt-2">
          <div class="mr-3">
            <a href="#"><i class="fas fa-search"></i></a>
          </div>
          <div class="mr-3">
            <a href="#"><i class="far fa-user"></i></a>
          </div>
          <div class="mr-3">
            <button type="button" class="btn btn-outline-danger">
              SPONSORSHIP
            </button>
          </div>
        </div>
      </div>
      <div class=" d-flex">
        <b-nav tabs v-for="tag in tags" :key="tag.id">
          <b-nav-item class="link">{{ tag.name }}</b-nav-item>
        </b-nav>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return { tags: [] }
  },
  created() {
    this.getTags()
  },
  methods: {
    getTags() {
      const urlTag = process.env.API_URL + 'tags'
      axios
        .get(urlTag)
        .then((response) => {
          this.tags = response.data
        })
        .catch(() => {
          alert('Hay un problema en Tags')
        })
    }
  }
}
</script>
<style>
a i {
  color: orangered;
}
.text-oranged {
  color: orangered;
}
.link {
  color: grey;
}
</style>
