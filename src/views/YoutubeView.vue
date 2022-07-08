<template>
  <HeaderC />
  <main id="main">
    <section id="youtube__cont">
      <TitleC name1="Youtube" name2="Book" />
      <div className="container">
        <div className="youtube__inner">
          <div className="youtube__search container">
            <form @submit.prevent="SearchYoutube()">
              <div>
                <label for="search" class="sr-only">검색하기</label>
                <input
                  v-model="search"
                  type="search"
                  id="search"
                  placeholder="검색어를 입력하세요"
                />
                <button type="submit" value="search">검색</button>
              </div>
            </form>

            <div className="youtube__list">
              <ul>
                <li v-for="youtube in youtubes" :key="youtube.id.videoId">
                  <a href="">
                    <img
                      :src="youtube.snippet.thumbnails.medium.url"
                      alt="movie.snippet.title"
                    />
                    <p>
                      {{ youtube.snippet.title }}
                    </p>
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
import { ref } from "vue";

export default {
  components: {
    HeaderC,
    FooterC,
    TitleC,
    ContactC,
  },

  setup() {
    const youtubes = ref("");
    const SearchYoutube = () => {
      let requestOptions = {
        method: "GET",
        redirect: "follow",
      };

      fetch(
        "https://youtube.googleapis.com/youtube/v3/search?part=snippet&maxResults=30&q=vue&key=AIzaSyDaygI-K29BFAJo5rA5Xh20T1_PASBNskw&type=video",
        requestOptions
      )
        .then((response) => response.json())
        .then((data) => {
          youtubes.value = data.items;
        })
        .catch((error) => console.log("error", error));
    };
    SearchYoutube();

    return { youtubes, SearchYoutube };
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
        color: var(--black);
        font-family: var(--sub_font2);
        padding-top: 7px;
      }
    }
  }
}
.youtube__search {
  position: relative;

  label {
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
