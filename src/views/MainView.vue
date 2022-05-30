<template>
  <HeaderC />
  <main id="main">
    <section className="main__cont">
      <div className="main__inner">
        <div>WE PROVIDE</div>
        <div>VISUAL CODING</div>
        <div>SOLUTIONS</div>
        <div>FOR YOU WEBS</div>
      </div>
    </section>
  </main>
  <FooterC />
</template>

<script>
import HeaderC from "@/components/HeaderC.vue";
import FooterC from "@/components/FooterC.vue";

export default {
  components: {
    HeaderC,
    FooterC,
  },
};
</script>

<style lang="scss">
.main__cont {
  background: var(--light_bg);
  justify-content: center;
  align-items: center;
  display: flex;
  height: 100vh;

  .main__inner {
    font-size: 10vw;
    line-height: 0.85;
    font-family: "Saol";
    color: var(--black);
    text-transform: uppercase;
  }
}
</style>
