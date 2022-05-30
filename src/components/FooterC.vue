<template>
  <footer id="footer">
    <div>
      <h4>Email</h4>
      <a href="mailto:dnwls7738@naver.com">dnwls7738@naver.com</a>
    </div>
    <div>
      <h4>kakao</h4>
      <a href="#">zxcv5274</a>
    </div>
    <div>
      <h4>social</h4>
      <ul>
        <li>
          <a href="https://www.youtube.com/channel/UCuaqGba8-mt9QSOE9HtJX9g"
            >Youtube</a
          >
        </li>
        <li><a href="https://www.instagram.com/wooo_j2/">Instargram</a></li>
        <li><a href="https://github.com/dnwls7738">Github</a></li>
        <li>
          <a href="https://dnwls7738.github.io/webs_class/refer/index.html"
            >Reference</a
          >
        </li>
        <li><a href="#">Tutorials</a></li>
      </ul>
    </div>
  </footer>
</template>

<style lang="scss">
#footer {
  position: fixed;
  left: 0;
  bottom: 0;
  width: 100%;
  color: var(--black);
  border-top: 1px solid var(--light_border);
  background-color: var(--light_bg);
  display: flex;
  align-items: center;
  font-family: "Rajdhani";
  div {
    text-align: center;
    padding: 1.45rem;
  }
  h4,
  ul {
    display: inline-block;
  }
  a {
    position: relative;
    &::before {
      content: "";
      position: absolute;
      left: 0;
      bottom: 0;
      width: 100%;
      height: 1px;
      background: var(--white);
      transform: scaleX(0);
      transition: all 0.3s ease;
    }
    &:hover::before {
      transform: scaleX(1);
    }
  }
  h4 {
    font-weight: 600;
    padding: 0 0.6em;
    text-transform: capitalize; //앞글자만 대문자
  }
  div:nth-child(1) {
    flex: 1 1 25%;
    border-right: 1px solid var(--light_border);
  }
  div:nth-child(2) {
    flex: 1 1 20%;
    border-right: 1px solid var(--light_border);
  }
  div:nth-child(3) {
    flex: 1 1 55%;
    li {
      display: inline;
      a {
        display: inline-block;
        padding: 0 0.6em;
        position: relative;
        &::before {
          content: "";
          position: absolute;
          left: 0.6rem;
          bottom: 0;
          width: calc(100% - 1.2em);
          height: 1px;
          background: var(--white);
          transform: scaleX(0);
          transition: all 0.3s ease;
        }
        &:hover::before {
          transform: scaleX(1);
        }
      }
    }
  }
}

// 라이트 버전
.light#footer {
  background-color: var(--light_bg);
  border-color: var(--light_border);
  h4 {
    color: var(--black);
  }
  a {
    color: var(--black);
    &::before {
      background: var(--black);
    }
  }
  div {
    border-right-color: var(--light_border);
    li {
      a {
        &::before {
          background: var(--black);
        }
      }
    }
  }
}

// 미디어쿼리
@media (max-width: 1000px) {
  #footer {
    div:nth-child(1) {
      h4 {
        display: none;
      }
    }

    div:nth-child(2) {
      display: none;
    }

    div:nth-child(3) {
      display: none;
    }
  }
}
</style>
