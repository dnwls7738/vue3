<template>
  <HeaderC />
  <main id="main">
    <section id="movie__cont">
      <TitleC name1="Moive" name2="Book" />
      <div className="container">
        <div className="movie__inner">
          <div className="movie__search container">
            <form @submit.prevent="SearchMovie()">
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
          </div>
          <div className="movie__list">
            <ul>
              <li v-for="movie in movies" :key="movie.id">
                <a href="">
                  <img
                    :src="
                      `https://image.tmdb.org/t/p/w500/` + movie.poster_path
                    "
                    :alt="movie.title"
                  />
                  <p className="title">{{ movie.title }}</p>
                </a>
              </li>
            </ul>
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
    const movies = ref([]);
    let search = ref("avatar");
    const SearchMovie = () => {
      let requestOptions = {
        method: "GET",
        redirect: "follow",
      };

      fetch(
        `https://api.themoviedb.org/3/search/movie?api_key=fcb26c48d7a8344d8d79fca80a3681c6&query=${search.value}`,
        requestOptions
      )
        .then((response) => response.json())
        .then((data) => {
          {
            movies.value = data.results;
            search.value = "";
            console.log(movies);
          }
        })
        .catch((error) => console.log("error", error));
    };
    SearchMovie();

    return { movies, search, SearchMovie };
  },
};
</script>

<style lang="scss">
.movie__list {
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
.movie__search {
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
    width: 100%;
    background: var(--black);
    border-radius: 50px;
    padding: 1rem 3rem 1rem 2rem;
    color: var(--white);
    font-family: var(--subKor_font);
    margin-bottom: 1%;
  }
  button {
    position: absolute;
    top: 12px;
    right: 15px;
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
  .movie__list {
    ul {
      li {
        flex: 1 1 43%;
        display: block;
        img {
          width: 100%;
        }
        p {
          color: var(--white);
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
  .movie__list {
    ul {
      li {
        flex: 1 1 43%;
        display: block;
        img {
          width: 100%;
        }
        p {
          color: var(--white);
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
