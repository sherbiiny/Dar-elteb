<template>
  <main class="Majors">
    <h1>التخصصات المقترحة و المخطط انشائها ضمن المشروع</h1>
    <h2>- مستشفي دار الطب بالمنصورة -</h2>
    <div class="btn-cont" data-aos="fade-up">
      <v-btn v-for="btn in btns" :key="btn.major">{{ btn.major }}</v-btn>
    </div>
  </main>
</template>

<script>
export default {
  data() {
    return {
      btns: [
        {major: 'الباطنة و الغدد الصماء و السكر'},
        {major: 'الباطنة و الكبد و الجهاز الهضمي'},
        {major: 'الباطنة و الكلي'},
        {major: 'عيادة القلب'},
        {major: 'عيادة الاطفال'},
        {major: 'عيادة النفسية و العصبية'},
        {major: 'عيادة علاج الاورام'},
        {major: 'الجراحة العامة'},
        {major: 'علاج الألم'},
        {major: 'الجراحة و الأوعية الدموية'},
        {major: 'جراحة التجميل و الحروق'},
        {major: 'جراحة الاورام'},
        {major: 'عيادة النساء و التوليد'},
        {major: 'جراحة العيون'},
        {major: 'جراحة العظام'},
        {major: 'جراحة المخ و الاعصاب'},
        {major: 'جراحة القلب و الصدر'},
        {major: 'الانف و الأذن و الحنجرة'},
        {major: 'المسالك البولية'},
        {major: 'التحاليل الطبية'},
        {major: 'التحاليل الباثولوجية'},
        {major: 'الأشعة التشخيصية'},
        {major: 'الفم و الاسنـــان'},
        {major: 'التخاطب و السمعيات'},
        {major: 'جراحة الاطفال'},
        {major: 'جراحة المناظير'},
        {major: 'الروماتيزم و الطب الطبيعي'},
        {major: 'الجلدية و التناسلية و العقم'},
        {major: 'عيادة الامراض الصدرية'}
      ]  
    }
  },
}
</script>

<style lang="scss">
@import '../assets/config';

.Majors {
  text-align: center;
  padding: 50px;
  color: $prim;

  .btn-cont {
    display: grid;


    .v-btn {
      background: $prim !important;
      color: #ffffff;
      height: 50px;
      width: 240px;
      margin: auto;
    }
  

  }

  @media screen and (max-width: 600px) {

    h1 {
      font-size: 1.4em;
    }

    h2 {
      font-size: 1em;
      margin-top: 20px;
    }

    .btn-cont {
      margin-top: 70px;
      grid-template-columns: repeat(1, 1fr);
      gap: 10px;

      .v-btn {
        width: 240px;
        font-size: 1.1em;
      }
    }
  }


  @include MQ($sm) {
    .btn-cont {
      grid-template-columns: repeat(2, 1fr);
      gap: 30px;
      margin-top: 50px;
    }
  }

  @include MQ($md) {

    .btn-cont {
      grid-template-columns: repeat(3, 1fr);
      gap: 30px;
      margin-top: 20px;
      padding: 80px;

      .v-btn {
        font-size: 1.1em;
      }
    }
  }
}
</style>