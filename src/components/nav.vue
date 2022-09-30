<template>
  <div class="col-sm-10 main desktop">
    <div class="logo">
      <li>
        <img src="../assets/logo.png" />
        <span style="margin-left: 15px">CRAPPO</span>
      </li>
    </div>
    <nav class="nav">
      <ul>
        <li>Product</li>
        <li>Features</li>
        <li>About</li>
        <li>Contact</li>
        <li>Login</li>
        <li class="reg">Register</li>
      </ul>
    </nav>
  </div>

  <div class="col-sm-10 mobile">
    <div class="logo">
      <li>
        <img src="../assets/logo.png" />
        <span style="margin-left: 15px">CRAPPO</span>
      </li>
      <i class="fa fa-bars fa-2x" @click="toggle"></i>
    </div>
    <transition name="translateX">
      <nav class="mob" v-if="openNav == true">
        <ul>
          <li>Product</li>
          <li>Features</li>
          <li>About</li>
          <li>Contact</li>
          <li>Login</li>
          <li class="new">Register</li>
        </ul>
      </nav>
    </transition>
  </div>
</template>
<script>
export default {
  data() {
    return {
      openNav: false,
    };
  },
  methods: {
    toggle() {
      if (this.openNav == "") {
        return (this.openNav = true);
      }
      return (this.openNav = "");
    },
  },
};
</script>
<style scoped>
.main {
  display: flex;
  width: 90%;
  height: 50px;
  align-items: center;
  margin: auto;
}

.main > div {
  width: 100%;
}
.logo li {
  list-style: none;
  display: flex;
  align-items: center;
  color: white;
  margin-top: 50px;
}
.nav ul {
  list-style: none;
  display: flex;
  color: white;
  align-items: center;
  margin-top: 50px;
}
.nav li {
  margin: 10px;
}

.logo ul {
  list-style: none;
  display: flex;
  color: white;
  align-items: center;
}
.nav li {
  margin: 10px;
}
.nav li:hover {
  border-bottom: 2px solid green;
  cursor: pointer;
  padding: 10px 0px;
}
.mog {
  background: #3671e9;
}
.mobile {
  display: none;
}

@media only screen and (max-width: 600px) {
  .desktop {
    display: none;
  }
  .mobile {
    display: block;
    position: fixed;
    width: 100%;
    top: 0;
    left: 0;
  
  z-index: 1;
  }

  .mob ul {
    list-style: none;
    display: block;
    color: white;
    margin-top: 80px;
    padding: 0px;
    width: 40%;
    margin: auto;
    margin-top: 100px;
  }
  .mob li {
    margin: 30px 30px;
    font-weight: bold;
    text-align: center;
    color: white;
  }

  .logo {
    display: flex;
    align-items: center;
    margin-top: 0px;
    padding: 10px;
      z-index: 1;
       background: #0d0d2b;
   
  }

  .logo li {
    list-style: none;
    display: flex;
    align-items: center;
    color: white;
    margin-top: 3px;
  }
  .logo i {
    color: white;
    margin-left: 12rem;
    margin-top: 3px;
  }
  .nav li {
    margin: 10px;
  }
  .new {
    background: #3671e9;
    padding: 10px 0px;
    border-radius: 30px;
    text-align: center;
  }

  .mob {
    width: 100%;
    position: absolute;
    opacity: 10;
    right: 0;
    left: 0;
    height: 100vh;
    background: #0d0d2b;
  }

  .translateX-enter {
    transform: translateX(-200px);
    opacity: 0;
  }

  .translateX-enter-active,
  .translateX-leave-active {
    transform-origin: top left 0;
    transition: 3s ease;
  }

  .translateX-leave-to {
    transform: translateX(-200px);
    opacity: 0;
  }
}
</style>