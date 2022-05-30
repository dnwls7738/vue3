<template>
  <HeaderC />
  <main id="main">
    <section className="port__cont">
      <TitleC />
      <div className="container">
        <div className="portfolio__inner">
          <article className="port__item">
            <figure className="img">
              <a href=""><img src="" alt="" /></a>
            </figure>
            <div className="text">
              <h3></h3>
              <p></p>
            </div>
          </article>
        </div>
      </div>
    </section>
  </main>
  <ContactC />
  <FooterC />
</template>

<script>
import HeaderC from "@/components/HeaderC.vue";
import FooterC from "@/components/FooterC.vue";
import TitleC from "@/components/TitleC.vue";
import ContactC from "@/components/ContactC.vue";

export default {
  components: {
    HeaderC,
    FooterC,
    TitleC,
    ContactC,
  },
};
</script>

<style lang="scss">
// port__cont
.port__cont {
  padding-bottom: 20vh;
}
.portfolio__inner {
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
}
.port__item {
  flex: 1 1 30%;
  margin: 1%;

  .text {
    padding: 1.4rem;
    background-color: #151517;

    h3 {
      color: var(--black);
      font-family: var(--main_font);
      font-size: 2.6em;
      padding-top: 0.2em;
      text-transform: uppercase;
    }
    p {
      color: var(--black);
      font-family: var(--sub_font);
    }
  }
}
</style>
