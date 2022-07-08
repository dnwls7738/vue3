<template>
  <HeaderC />
  <main id="main">
    <section class="port__cont">
      <TitleC name1="Portfolio" name2="Book" />
      <div class="container">
        <div class="portfolio__inner">
          <article class="port__item" v-for="port in ports" :key="port.id">
            <figure class="img">
              <a :href="port.link" target="_blank">
                <img :src="port.image" :alt="port.title" />
              </a>
            </figure>
            <div class="text">
              <h3>{{ port.title }}</h3>
              <p>{{ port.category }}</p>
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
import { ref } from "vue";

export default {
  components: {
    HeaderC,
    FooterC,
    TitleC,
    ContactC,
  },

  setup() {
    const ports = ref([]);
    const Portfolios = () => {
      var requestOptions = {
        method: "GET",
        redirect: "follow",
      };
      fetch(
        "https://webstoryboy.github.io/dothome1/portfolio.json",
        requestOptions
      )
        .then((response) => response.json())
        .then((data) => (ports.value = data.data.ports))
        .catch((error) => console.log("error", error));
    };
    Portfolios();

    return { ports, Portfolios };
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
    background-color: var(--white);

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
