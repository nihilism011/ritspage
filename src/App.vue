<template>
  <div id="app">
    <div class="black-bg" v-if="infoState" @click="infoState = !infoState">
      <div class="white-bg" @click.stop>
        <img :src="require(`./assets/${info.infoimg}`)" />
      </div>
    </div>
    <div class="container">
      <div class="top-menu-bar">
        <a @click="bState = 'main'">Home</a>
        <a @click="bState = 'keyboard'">Keyboard</a>
        <a @click="bState = 'templates'">Templates</a>
        <a @click="bState = 'BoardBoard'">BoardBoard</a>
      </div>
      <MainBoard v-show="bState === 'main'" />
      <KeyboardBoard
        v-show="bState === 'keyboard'"
        :items="keyboards"
        @name-click="nameClick"
      />
      <TemplatesBoard v-show="bState === 'templates'" />
      <BoardBoard v-show="bState === 'BoardBoard'"></BoardBoard>
      <button @click="darkMode" id="darkBtn">
        <img :src="darkModeImage" alt="다크모드 전환" />
      </button>
    </div>
  </div>
</template>

<script>
import MainBoard from "./components/MainBoard.vue";
import KeyboardBoard from "./components/KeyboardBoard.vue";
import TemplatesBoard from "./components/TemplatesBoard.vue";
import BoardBoard from "./components/BoardBoard.vue";

export default {
  components: {
    MainBoard,
    KeyboardBoard,
    TemplatesBoard,
    BoardBoard,
  },
  data() {
    return {
      bState: "main",
      infoState: false,
      info: {},
      isDarkMode: false,
    };
  },
  computed: {
    darkModeImage() {
      return this.isDarkMode
        ? require("./assets/dark.light.png")
        : require("./assets/night.png");
    },
  },
  methods: {
    nameClick(item) {
      this.infoState = true;
      this.info = item;
    },
    darkMode() {
      this.isDarkMode = !this.isDarkMode;
      if (this.isDarkMode) {
        document.body.classList.add("dark-mode");
      } else {
        document.body.classList.remove("dark-mode");
      }
    },
  },
};
</script>

<style lang="scss">
/* 전역 스타일 */
body {
  transition: background-color 0.5s;

  &.dark-mode {
    background-color: #1e1e1e;
    color: #ffffff;

    .top-menu-bar {
      background-color: #3c3c3c;
    }

    .top-menu-bar a {
      color: #ffffff;
    }

    .white-bg {
      background-color: #2e2e2e;
      color: #ffffff;
    }

    .keyboard {
      color: #ffffff;
    }

    .show-box {
      background-color: white;
      transition: background-color 0.5s;
    }
    .box {
      background: white;
      transition: background-color 2s;
    }
  }
}

/* 컴포넌트 스타일 */
.top-menu-bar {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;

  a {
    color: white;
    padding: 10px 15px;
    cursor: pointer;

    &:hover {
      color: #6fbfea;
      transition: color 0.4s;
    }
  }
}

#darkBtn {
  position: fixed;
  right: 20px;
  bottom: 20px;
  background: none;
  border: none;
  cursor: pointer;

  img {
    width: 50px;
    height: 50px;
  }
}

.black-bg {
  display: flex;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  background: rgba(0, 0, 0, 0.6);
  position: fixed;
  justify-content: center;
  padding: 20px;
  z-index: 9999;
}

.white-bg {
  background: rgba(255, 255, 255, 0.7);
  border-radius: 8px;
  overflow: auto;
  padding: 0;

  img {
    width: 800px;
  }
}

h3 {
  cursor: pointer;
}

body .top-menu-bar,
body .top-menu-bar a,
body .keyboard {
  transition: background-color 0.5s, color 0.5s;
}

.container {
  transition: background-color 0.5s, color 0.5s;
}

/* 스크롤바 스타일 */
::-webkit-scrollbar {
  width: 12px;
  height: 8px;
}

::-webkit-scrollbar-track {
  background: #f1f1f1;
}

::-webkit-scrollbar-thumb {
  background-color: #6fbfea;
  border-radius: 10px;
  border: 2px solid #f1f1f1;
  min-height: 10%;
  min-width: 20px;

  &:hover {
    background: #5ba6d1;
  }
}
</style>
