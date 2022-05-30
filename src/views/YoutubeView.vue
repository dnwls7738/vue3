<template>
  <HeaderC />
  <main id="main">
    <section id="youtube__cont">
      <TitleC />
      <div className="container">
        <div className="youtube__inner">
          <div className="youtube__search container">
            <h2>검색하기</h2>
            <input
              ref="{inputRef}"
              type="search"
              placeholder="검색어를 입력하세요"
              onKeyPress="{onKeyPress}"
            />
            <button type="submit" onClick="{onClick}">검색</button>
            <div className="youtube__list">
              <ul>
                <li>
                  <a href="">
                    <img src="" alt="" />
                    <p></p>
                  </a>
                </li>
              </ul>
            </div>
          </div>
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
.youtube__list {
  ul {
    display: flex;
    flex-wrap: wrap;
    li {
      flex: 1 1 23%;
      margin: 1%;
      p {
        color: var(--white);
        font-family: var(--sub_font2);
        padding-top: 7px;
      }
    }
  }
}
.youtube__search {
  position: relative;

  h2 {
    color: var(--white);
    font-size: 40px;
    font-family: var(--subKor_font);
    text-indent: -9999px;
    width: 0;
    height: 0;
  }
  input {
    border: 1px solid var(--light_border);
    width: 98%;
    background: var(--black);
    border-radius: 50px;
    padding: 1rem 3rem 1rem 2rem;
    color: var(--white);
    font-family: var(--subKor_font);
    margin: 0 1%;
    margin-bottom: 1%;
  }
  button {
    position: absolute;
    top: 13px;
    right: 30px;
    background: transparent;
    border: 0;
    color: var(--black);
    width: 30px;
    height: 30px;
    border-radius: 50%;
    background: var(--light_bg);
    font-size: 12px;
    font-family: var(--subKor_font);
    transition: opacity 0.3s ease;

    &:active {
      opacity: 0.7;
    }
  }
}

@media (max-width: 1000px) {
  .youtube__list {
    ul {
      li {
        flex: 1 1 43%;
        display: block;
        img {
          width: 100%;
        }
        p {
          color: var(--black);
          overflow: hidden;
          text-overflow: ellipsis;
          display: -webkit-box;
          -webkit-line-clamp: 3;
          -webkit-box-orient: vertical;
        }
      }
    }
  }
}
@media (max-width: 600px) {
  .youtube__list {
    ul {
      li {
        flex: 1 1 43%;
        display: block;
        img {
          width: 100%;
        }
        p {
          color: var(--black);
          overflow: hidden;
          text-overflow: ellipsis;
          display: -webkit-box;
          -webkit-line-clamp: 3;
          -webkit-box-orient: vertical;
        }
      }
    }
  }
}
</style>
