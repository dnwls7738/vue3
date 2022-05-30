<template>
  <section class="cont__title">
    <div class="container">
      <h1>
        <strong>About</strong>
        <em>Me</em>
      </h1>
    </div>
  </section>
</template>

<style lang="scss">
// cont__title
.cont__title {
  padding: 15vmax 1% 10vmax;
  font-size: 5vmax;
  font-family: var(--main_font);
  text-transform: uppercase;
  line-height: 0.85;
  color: var(--black);

  em {
    display: block;
  }
}

@media (max-width: 600px) {
  .cont__title {
    text-align: center;
    padding-bottom: 10vw;
  }
}
</style>
