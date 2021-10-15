<template>
  <div class="home">
    <rain-of-flowers />
    <div class="content">
      <div>
        <img class="home-logo" src="../assets/img/catcat.jpg" />
      </div>
      <div class="home-body">
        <div class="list">
          <router-link class="link" to="/articles"> 明月策 </router-link>
          <a target="_blank" class="link" href="#"> GitHub </a>
          <router-link class="link" to="/diaries"> 随笔 </router-link>
          <router-link class="link" to="/buger"> Bug儿 </router-link>
          <router-link class="link" to="/author"> 关于作者 </router-link>
        </div>
        <div class="newUser">
          <router-link class="link" to="/login"> 登录 </router-link>
          <router-link class="link" to="/register"> 注册 </router-link>
          <router-link class="link" to="/admin"> 后台管理 </router-link>
        </div>
        <div class="introduce">离恨恰如春草，渐行渐远还生</div>
      </div>
    </div>
  </div>
</template>

<script>
import RainOfFlowers from "../components/common/RainOfFlowers.vue";
export default {
  components: { RainOfFlowers },
  name: "Home",
};
</script>

<style lang="less">
.home {
  position: fixed;
  left: 0;
  top: 0;
  .content {
    position: fixed;
    left: 0;
    top: 0;
    right: 0;
    bottom: 0;
    font-size: 20px;
    text-align: center;
    padding-top: 12%;
    .home-logo {
      width: 144px;
      border-radius: 50%;
      animation: mylogo 3s;
      -moz-animation: mylogo 3s; // Firefox
      -webkit-animation: mylogo 3s; // Safari and Chrome
      -o-animation: mylogo 3s; // Opera
      animation-iteration-count: 1;
    }
    .home-body {
      padding-top: 20px;
      .list {
        .link {
          display: inline-block;
          padding: 20px;
          color: #002f5c;
          min-width: 80px;
          font-size: 25px;
        }
        .link:hover {
          text-shadow: 0 0 10px yellowgreen,
                       0 0 20px yellowgreen,
                       0 0 30px yellowgreen,
                       0 0 40px yellowgreen,
        }
      }
      .newUser {
        padding-top: 20px;
        .link{
          display: inline-block;
          padding: 20px;
          color: #003c96;
          min-width: 80px;
          font-size: 22px;
        }
        .link:hover {
          text-shadow: 0 0 10px rgb(224, 221, 40),
                       0 0 20px rgb(224, 221, 40),
                       0 0 30px rgb(224, 221, 40),
                       0 0 40px rgb(224, 221, 40),
        }
      }
    }
    .introduce {
      padding-top: 100px;
      color: #fff;
      font-family: "Brush Script MT", cursive;
    }
  }
}
a {
  text-decoration: none;
}
a:hover {
  text-decoration: none;
}
@keyframes mylogo {
  0% {
    transform: rotate(0deg) scale(1, 1);
    opacity: 1;
  }
  25% {
    transform: rotate(0deg) scale(1.2, 1.2);
    opacity: 0.8;
  }
  100% {
    transform: rotate(0deg) scale(1, 1);
    opacity: 1;
  }
}

@-moz-keyframes mylogo {
  0% {
    transform: rotate(0deg) scale(1, 1);
    opacity: 1;
  }
  25% {
    transform: rotate(0deg) scale(1.2, 1.2);
    opacity: 0.8;
  }
  100% {
    transform: rotate(0deg) scale(1, 1);
    opacity: 1;
  }
}

@-webkit-keyframes mylogo {
  0% {
    transform: rotate(0deg) scale(1, 1);
    opacity: 1;
  }
  25% {
    transform: rotate(0deg) scale(1.2, 1.2);
    opacity: 0.8;
  }
  100% {
    transform: rotate(0deg) scale(1, 1);
    opacity: 1;
  }
}

@-o-keyframes mylogo {
  0% {
    transform: rotate(0deg) scale(1, 1);
    opacity: 1;
  }
  25% {
    transform: rotate(0deg) scale(1.2, 1.2);
    opacity: 0.8;
  }
  100% {
    transform: rotate(0deg) scale(1, 1);
    opacity: 1;
  }
}
</style>
