<template>
  <div>
  <GalleryPage></GalleryPage>
</div>
</template>

<script>
import TopNav from '../components/nav/TopNav.vue'
import GalleryPage from './gallery.vue'
export default {
  name: 'IndexPage',
  components: { TopNav,GalleryPage}
}
</script>
