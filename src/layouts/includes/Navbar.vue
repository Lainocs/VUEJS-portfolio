<template>
    <div id="topnav" class="topnav">
        <span id="home_link" class="topnav_link" @click="changeActive(1)"><img :src="require('@/assets/images/logo.png')" width="50"></span>

        <!-- Classic Menu -->
        <nav role="navigation" id="topnav_menu">
            <span class="topnav_link" @click="changeActive(2)">PROJECTS</span>
            <span class="topnav_link" @click="changeActive(3)">CONTACT</span>
        </nav>

        <a id="topnav_hamburger_icon" href="javascript:void(0);" @click="showResponsiveMenu()">
        <!-- Some spans to act as a hamburger -->
            <span></span>
            <span></span>
            <span></span>
        </a>

        <!-- Responsive Menu -->
        <nav role="navigation" id="topnav_responsive_menu">
            <ul>
                <li><span class="topnav_link" @click="changeActive(2)">PROJECTS</span></li>
                <li><span class="topnav_link" @click="changeActive(3)">CONTACT</span></li>
            </ul>
        </nav>
    </div>
</template>

<script>
    export default {
        name: 'Navbar',
        data() {
            return {
                activePage: 1,
            }
        },
        methods: {
            showResponsiveMenu() {
                var menu = document.getElementById("topnav_responsive_menu");
                var icon = document.getElementById("topnav_hamburger_icon");
                if (menu.className === "") {
                    menu.className = "open";
                    icon.className = "open";
                } else {
                    menu.className = "";                    
                    icon.className = "";
                }
            },
            changeActive(id) {
                this.activePage = id;
                this.$emit('active-page', id);
            }
        },
    }
</script>

<style>
    /* ******************** NAV BAR ******************** */
.topnav {
  background-color: #161616;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
}
.topnav_link {
  cursor: pointer;
  color: white;
  padding: 15px;
  text-decoration: none;
}
.topnav_link:hover {
  color: #575757;
}

/* hide responsive menu */
#topnav_hamburger_icon,
#topnav_responsive_menu {
  display: none;
}

@media only screen and (max-width: 768px) {
  /* hide classic menu */
  #topnav_menu {
    display: none;
  }

  /* position home link at left and hamburger at right */
  #home_link {
    flex-grow: 1;
    text-align: left;
  }

  /* disable horizontal scrolling  */
  #root {
    position: relative;
    overflow-x: hidden;
  }

  /* show responsive menu and position at the right of the screen */
  #topnav_responsive_menu {
    display: block;
    position: absolute;
    margin: 0;
    right: 0;
    top: 0;
    width: 100vw;
    height: 100vh;

    z-index: 99;

    transform-origin: 0% 0%;
    transform: translate(200%, 0);

    transition: transform 0.5s cubic-bezier(0.77, 0.2, 0.05, 1);
  }

  #topnav_responsive_menu ul {
    display: flex;
    flex-direction: column;

    position: absolute;
    margin: 0;
    right: 0;
    top: 0;

    min-width: 50vw;
    height: 100vh;
    padding: 56px 0 0;

    text-align: center;

    background: #161616;
    list-style-type: none;
    -webkit-font-smoothing: antialiased;
  }

  #topnav_responsive_menu li {
    padding: 12px 24px;
  }

  #topnav_responsive_menu a {
    white-space: nowrap;
    color: #fff;
    text-decoration: none;
  }

  /* And let's slide it in from the right */
  #topnav_responsive_menu.open {
    transform: none;
    position: fixed;
  }

  /* ******************** HAMBURGER ICON ******************** */
  /* define size and position of the hamburger link */
  #topnav_hamburger_icon {
    display: block;
    position: relative;
    margin: 16px;
    width: 33px;
    height: 28px;

    z-index: 100;

    -webkit-user-select: none;
    user-select: none;
    cursor: pointer;
  }

  /* define the style (size, color, position, animation, ...) of the 3 spans */
  #topnav_hamburger_icon span {
    display: block;
    position: absolute;
    height: 4px;
    width: 100%;
    margin-bottom: 5px;

    background: #ededed;
    border-radius: 3px;

    z-index: 100;

    opacity: 1;
    left: 0;

    -webkit-transform: rotate(0deg);
    -moz-transform: rotate(0deg);
    -o-transform: rotate(0deg);
    transform: rotate(0deg);
    -webkit-transition: 0.25s ease-in-out;
    -moz-transition: 0.25s ease-in-out;
    -o-transition: 0.25s ease-in-out;
    transition: 0.25s ease-in-out;
  }

  /* set the 3 spans position to look like a hamburger */
  #topnav_hamburger_icon span:nth-child(1) {
    top: 0px;
    -webkit-transform-origin: left top;
    -moz-transform-origin: left top;
    -o-transform-origin: left top;
    transform-origin: left top;
  }
  #topnav_hamburger_icon span:nth-child(2) {
    top: 12px;
    -webkit-transform-origin: left center;
    -moz-transform-origin: left center;
    -o-transform-origin: left center;
    transform-origin: left center;
  }
  #topnav_hamburger_icon span:nth-child(3) {
    top: 24px;
    -webkit-transform-origin: left bottom;
    -moz-transform-origin: left bottom;
    -o-transform-origin: left bottom;
    transform-origin: left bottom;
  }

  /* change color when opening the menu */
  #topnav_hamburger_icon.open span {
    background: #333;
  }

  /* the first span rotates 45° \ */
  #topnav_hamburger_icon.open span:nth-child(1) {
    width: 110%;
    -webkit-transform: rotate(45deg);
    -moz-transform: rotate(45deg);
    -o-transform: rotate(45deg);
    transform: rotate(45deg);
  }

  /* the second span disappears */
  #topnav_hamburger_icon.open span:nth-child(2) {
    width: 0%;
    opacity: 0;
  }

  /* the last span rotates -45° / */
  #topnav_hamburger_icon.open span:nth-child(3) {
    width: 110%;
    -webkit-transform: rotate(-45deg);
    -moz-transform: rotate(-45deg);
    -o-transform: rotate(-45deg);
    transform: rotate(-45deg);
  }
}
</style>