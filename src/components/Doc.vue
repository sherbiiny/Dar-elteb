<template>
  <main class="Doc">
    <v-container>
      <v-row>
        <v-col md="6" class="text" data-aos="fade-up">
          <h2>مستشفي دار الطب بالمنصورة</h2>
          <h4>"زود فرص ارباحك باستثمارك و عملك معنا"</h4>
          <div class="box">ضمن نخبة من اكبر المستثمرين و الأطباء بالدقهلية</div>
        </v-col>
        <v-col md="6" data-aos="fade-up" data-aos-delay="500">
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
    margin-top: 100px;
    padding-right: 100px;
    text-align: center;

    h2 {
      font-size: 3em;
    }

    h4 {
      font-size: 1.5em;
      margin-top: 20px;
    }

    .box {
      border: 2px solid $prim;
      border-radius: 5px;
      font-size: 2.4em;
      font-weight: 600;
      max-width: 400px;
      margin: auto;
      padding: 20px;
      margin-top: 100px;
      cursor: pointer;
      user-select: none
    }
  }
}
</style>