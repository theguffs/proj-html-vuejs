<script>
export default {
  data() {
    return {
      mainMenu: [
        { name: "Home" },
        { name: "Pages" },
        { name: "Courses" },
        { name: "Features" },
        { name: "Blog" },
        { name: "Shop" },
      ],
      languages: [
        {
          flag:"/public/flag/en.png",
          language: "ENGLISH",
        },
        {
          flag:"/public/flag/fr.png",
          language: "FRANCAIS",
        },
        {
          flag:"/public/flag/de.png",
          language: "DEUTSCH",
        },
      ],
      currentLanguage: 0,
      dropdownOpen: false,
    };
  },
  mounted() {
    this.currentLanguage = this.languages[0]; 
  },
  methods: {
    toggleDropdown() {
      this.dropdownOpen = !this.dropdownOpen;
    },
    selectLanguage(lang) {
      this.currentLanguage = lang;
      this.dropdownOpen = false;
    },
  },
};
</script>

<template>
  <header class="navbar">
    <div class="container">

      <!-- logo -->

      <div class="logo">
        <img src="../assets/business/images/dark-logo.png" alt="Logo" />
      </div>

      <!-- main navigation Menu -->

      <nav class="nav-menu">
        <ul>
          <li v-for="item in mainMenu" :key="item.name">
            <a href="#">{{ item.name }} 
              <span>▼</span>
            </a>
          </li>
        </ul>
      </nav>

      <!-- menù a destra-->

      <div class="right-menu">

        <!-- lingua -->

          <div class="language-selector" @click="toggleDropdown">
            <img v-if="currentLanguage" :src="currentLanguage.flag" alt="Language Flag" class="flag-icon" />
            <span v-if="currentLanguage">{{ currentLanguage.language }}</span>
            <span>▼</span>

          <!-- Dropdown Menu -->

          <ul v-if="dropdownOpen" class="dropdown">
            <li v-for="lang in languages" :key="lang.language" @click="selectLanguage(lang)">
              <img :src="lang.flag" class="flag-icon" />
              {{ lang.language }}
            </li>
          </ul>
        </div>

        <!-- user icon -->
         
        <i class="fa-regular fa-circle-user"></i>
        <div class="search-bar">
          <input type="text" placeholder="Search..." />
        </div>
      </div>
    </div>
  </header>
</template>

<style lang="scss" scope>

$primary-color: #61e6d2;
$hover-color: #333;

.navbar {
  background-color: white;
  padding: 20px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);

  .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .logo img {
    max-height: 50px;
  }

  .nav-menu {
    ul {
      list-style: none;
      display: flex;
      gap: 30px;

      li {
        a {
          text-decoration: none;
          color: $hover-color; 
          font-size: 16px;
          font-weight: 600;
          display: inline-block;
          transition: color 0.3s ease; 

          &:hover {
            color: $primary-color; 
            border-bottom: $primary-color solid 2px;
          }
        }
      }
    }
  }

  .right-menu {
    display: flex;
    align-items: center;
    gap: 20px;

    .language-selector {
      display: flex;
      align-items: center;
      cursor: pointer;
      position: relative;

      .flag-icon {
        width: 24px;
        margin-right: 8px;
      }

      .dropdown {
        position: absolute;
        top: 40px; 
        right: 0;
        background-color: white;
        border: 1px solid #ccc;
        box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        list-style: none;
        padding: 10px;
        display: flex; 
        flex-direction: column;
        z-index: 11;
      
        li {
          padding: 5px 0;
          cursor: pointer;
        }
      }
    }

    .search-bar {
      position: relative;

      input {
        border: none;
        border-bottom: 1px solid #ccc;
        padding: 5px;
      }

      i {
        position: absolute;
        right: 10px;
        top: 50%;
        transform: translateY(-50%);
        color: #888;
      }
    }
  }
}
</style>