<template>
  <div>
    <TopNav />
    <BigImg :image="img" @rm="runModal($event)" />
    <SmallImage :image="items" @selectedImg="showImg($event)" />
    <Modal
      v-show="showModal"
      :image="img"
      :images="items"
      @nextImage="nextImg($event)"
      @closeModel="runModal($event)"
      @previousImage="previousImg($event)"
      @showImage="showImg($event)"
    />
  </div>
</template>

<script>
import TopNav from "../components/nav/TopNav.vue";
import SmallImage from "../components/gallery/smallImage.vue";
import BigImg from "~/components/gallery/bigImage.vue";
import Modal from "~/components/modals/modal.vue";

export default {
  name: "GalleryPage",
  components: { BigImg, TopNav, SmallImage, Modal },
  data() {
    return {
      items: [
        "https://trojka.polskieradio.pl/_next/image?url=https%3A%2F%2Fstatic.prsa.pl%2Fimages%2Fd9825012-e3fd-49e5-898b-b419235013a7.file&w=1920&q=75",
        "http://zachwyconanatura.pl/wp-content/uploads/2017/09/2-Gatunki-pelikan%C3%B3w-z-Delty-Dunaju-%E2%80%93-r%C3%B3%C5%BCowe-i-k%C4%99dzierzawe-5-770x514.jpg",
        "https://fajnepodroze.pl/wp-content/uploads/2020/10/pelikany.jpg",
        "https://www.pelikan.com/images/company/Company_image_4.jpg",
        "https://zoo.gda.pl/wp-content/uploads/pelikan-2-1350x900.jpg",
        "https://www.kreiszeitung-wesermarsch.de/Bilder/Pelikane-leben-unter-anderem-im-Donaudelta-In-Deutschland-158692.jpg",
      ],
      img: "https://thumbs.dreamstime.com/b/pelikan-22975323.jpg",
      selectedIndex: 0,
      showModal: false
    };
  },

  methods: {
    nextImg(){
      this.selectedIndex = (this.selectedIndex + 1) % this.items.length
      this.img = this.items[this.selectedIndex]
    },
    previousImg(){
      if(this.selectedIndex==0){
        this.selectedIndex= this.items.length-1}
      else{ 
        this.selectedIndex = (this.selectedIndex - 1) % this.items.length}  
      this.img = this.items[this.selectedIndex]

    },
    showImg(selectedImage) {
      this.img = selectedImage.url;
      this.selectedIndex = selectedImage.index;
    },
    runModal(e) {
      this.showModal = e;
    },
  },
};
</script>
