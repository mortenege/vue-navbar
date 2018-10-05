<template>
  <div class="navbar" :class="{ open: open }" id="navbar">
    <div class="logo">LOGO</div>

    <a href="javascript:void(0);" class="burger" @click="toggleMenu"><i class="fa fa-bars"></i></a>

    <div class="navclear"></div>
    
    <div class="topnav">
      <a href="#home" class="navelement navlink active">Home</a>
      <div href="javascript:void(0)" class="navelement navlink navdropdown" @click="openSubMenu">
        Dropdown
        <div class="subnav">
          <a href="#" class="navelement navlink">Link #1</a>
          <a href="#" class="navelement navlink">Link #1</a>
          <a href="#" class="navelement navlink">Link #1</a>
          <a href="#" class="navelement navlink">Link #1</a>
        </div>
      </div>
      <a href="#contact" class="navelement navlink">Contact</a>
      <a href="#about" class="navelement navlink">About</a>
    </div>
    
  </div>
</template>

<script>
export default {
  name: 'navbar',
  data() {
    return {
      open: false
    }
  },
  methods: {
    openMenu () {
      this.open = true
    },
    closeMenu () {
      this.open = false
    },
    toggleMenu () {
      this.open = !this.open
    },
    openSubMenu (e) {
      var nav = e.target.getElementsByClassName('subnav')
      
      if (nav.length > 0) {
        nav = nav[0]
      }

      nav.classList.toggle('open')
    }
  }
}
</script>

<style lang="scss">
.navbar {
  position: fixed;
  display: block;
  top: 0;
  left: 0;
  right: 0;
  margin: 0;
  padding: 0;
  color: #f2f2f2;
  background-color: #333;
  font-size: 17px;
}

.navbar .logo {
  display: block;
  float: left;
  padding: 14px 10px;
}

.navbar .navlink {
  color: inherit;
  text-decoration: inherit;
}

.navbar .burger {
  float: right;
  padding: 14px 10px;
  color: inherit;
}

.navbar .topnav {
  display: none;
  margin: 0;
  padding: 0;
}

.navbar.open .topnav {
  display: block;
}

.navbar .navelement {
  cursor: pointer;
  float: none;
  display: block;
  text-align: left;
  padding: 14px 20px;
  text-decoration: none;
}

.navbar .subnav {
  display: block;
  margin-top: 10px;
  max-height: 500px;
  overflow: hidden;
  transition: max-height 0.15s ease-in;
}

.navbar .subnav:not(.open) {
  max-height: 0;
  transition: max-height 0.25s ease-out;
}

.navbar .subnav .navelement {
  float: none;
  display: block;
  text-align: left;
  padding: 5px 10px;
  text-decoration: none;
}

.navbar .navclear {
  clear:both;
}

@media screen and (min-width: 600px) {
  .navbar .burger {
    display: none;
  }

  .navbar .navclear {
    clear:none;
  }

  .navbar .topnav {
    display: block;
    float: right;
  }

  .navbar .navelement {
    float: left;
  }

  .navbar .navdropdown {
    position: relative;
  }

  .navbar .subnav {
    position: absolute;
    right: 0;
    background-color: #333;
    min-width: 200px;
  }
  
}
</style>