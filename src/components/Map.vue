<template>
  <main class="Map">
    <v-row>

      <v-col md="6" class="form-col" data-aos="fade-up">
        <form>
          <input type="text" placeholder="الاسم">
          <input type="text" placeholder="رقم التليفون">
          <input type="email" placeholder="البريد الالكتروني">
          <textarea placeholder="الرسالة"></textarea>
          <v-btn type="submit" height="50" class="submit">ارسال</v-btn>
        </form>
      </v-col>

      <v-col md="6" class="map-col" data-aos="fade-up" data-aos-delay="500">
        <div class="map-box" id="map"></div>
      </v-col>
    </v-row>
  </main>
</template>

<script>

export default {

  mounted() {
    let map = new google.maps.Map(document.querySelector('#map'), {
        center: {lat: 31.036073, lng: 31.357698},
        zoom: 20,
    })

    let marker = new google.maps.Marker({
      position: {lat: 31.036073, lng: 31.357698},
      map: map
    });
  },
}
</script>

<style lang="scss">
@import '../assets/config';

.Map {
  background: #FAFAFA;

  .form-col {
    padding: 50px;

    form {
      display: grid;

      input, textarea {
        background: #FFF;
        margin: 30px 0;
        padding: 20px;

        &::placeholder {
          color: #999 !important;
        }
      }

      .submit {
        background: $prim !important;
        color: #FFF;
        width: 200px;
        margin: auto;
        font-size: 1.2em;
      }
    }
  }

  .map-col {
    display: grid;
    align-items: center;
    justify-content: center;
  } 

  .map-box {
    width: 500px;
    height: 500px;
    border-radius: 5px;
  }
}

@media screen and (max-width: 960px){
  .map-col {
    padding: 20px;
  }
  .map-box {
    width: 400px !important;
    height: 400px !important;
  }
}

// @include MQ($md) {
//   .map-box {
//     width: 400px !important;
//     height: 400px !important;
//   }
// }
</style>