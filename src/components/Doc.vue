<template>
  <main class="Doc">
    <v-container class="pb-0">
      <v-row>
        <v-col class="text col-8" sm="6" data-aos="fade-up">
          <h2>مستشفي دار الطب بالمنصورة</h2>
          <h4>"زود فرص ارباحك باستثمارك و عملك معنا"</h4>
          <div class="box">ضمن نخبة من اكبر المستثمرين و الأطباء بالدقهلية</div>
        </v-col>
        <v-col class="col-4 pb-0" sm="6" data-aos="fade-up" data-aos-delay="500">
          <img src="../assets/img/doc.png">
        </v-col>
      </v-row>
    </v-container>
  </main>
</template>

<style lang="scss">
@import '../assets/config';

.Doc {
  color: $prim;

  .text {
    text-align: center;

    .box {
      border: 2px solid $prim;
      border-radius: 5px;
      font-weight: 600;
      margin: auto;
      padding: 20px;
      cursor: pointer;
      user-select: none
    }
  }

  img {
    margin-bottom: -5px;
  }
}

@media screen and (max-width: 600px){
  .Doc {

    img {
      max-width: none !important;
      height: 250px;
      width: 250px;
      position: absolute; 
      z-index: -4 !important;
      right: -130px;
      bottom: 0px;
    }
    
    .text {
      margin-top: 50px;

      h2 {
        font-size: 1.2em;
      }

      h4 {
        margin: 30px 0;
        font-size: 1em;
      }

      .box {
        width: 150px;
        font-size: 1em;
      }
    }
  }
}

@include MQ($sm) {
  .Doc {
    
    .text {
      margin-top: 50px;

      h2 {
        font-size: 2em;
        white-space: nowrap;
      }

      h4 {
        font-size: 1.2em;
        margin: 30px auto;
      }

      .box {
        width: 220px;
        font-size: 1.4em;
      }
    }
  }
}

@include MQ($md) {
  .Doc {
      padding: 0 30px;

    .text {

      h2 {
        font-size: 3em;
      }

      h4 {
        font-size: 1.6em;
        margin: 30px 0;
      }

      .box {
        width: 300px;
        font-size: 1.5em;
      }
    }
  }
}
@include MQ($lg) {
  .Doc {
    padding: 0 150px;
  }
}

</style>