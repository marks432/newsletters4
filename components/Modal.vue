<template>
  <div>
    <div class="bg-black absolute pin-t pin-l h-screen.w-full">
      <div class="bg-white p-4 w-1/3">
        <div class="container">
          <div class="row">
            <div class="col-md-3 d-flex" :key="New.id">
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
</template>
<script>
export default {
    
}
</script>