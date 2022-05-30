<template>
  <HeaderC />
  <main id="main">
    <section className="refer__cont">
      <TitleC />
      <div className="container">
        <div className="refer__inner">
          <h2>CSS</h2>
          <ul className="refer__list"></ul>
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
.refer__cont {
  background-color: var(--light_bg);
  min-height: 100vh;
}
.refer__inner {
  h2 {
    color: var(--black);
    font-size: 2rem;
    margin-bottom: 1rem;
  }
}
.refer__list {
  border-top: 2px solid var(--light_border);
  border-bottom: 2px solid var(--light_border);
  a {
    display: block;
    color: var(--black);
    display: flex;
    align-items: center;
    justify-content: space-between;
    border-bottom: 1px solid var(--light_border);
    padding: 1.3rem 0;
    transition: all 0.3s;
    font-family: var(--sub_font2);
    &:hover {
      background: rgba(240, 238, 235, 0.5);
      color: var(--black);
    }
    span {
      display: inline-block;
    }
    span:nth-child(1) {
      width: 6%;
      text-align: center;
    }
    span:nth-child(2) {
      width: 20%;
    }
    span:nth-child(3) {
      width: 64%;
    }
    span:nth-child(4) {
      width: 10%;
      text-align: center;
    }
  }
}
.refer__table {
  margin-top: 200px;
  color: var(--black);
  font-family: var(--sub_font2);
  h3 {
    font-size: 3rem;
  }
  p {
    background-color: var(--light_bg);
    color: var(--black);
    padding: 1.4em;
  }
  .table {
    color: var(--black);
    font-family: var(--sub_font2);
    border: 1px solid var(--light_bg);
    margin-top: 0.5em;
    th,
    td {
      padding: 1em;
      font-weight: normal;
      border-bottom: 1px solid var(--light_border);
      border-left: 1px solid var(--light_border);
    }
  }
}
</style>
