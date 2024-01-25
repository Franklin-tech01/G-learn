<!-- <template>
    <nav>
        <h1>G-learn</h1>
        
        <ul>
            <li><router-link to="/">Home</router-link></li>
            <li><router-link to="/about">About</router-link></li>
            <li><router-link to="/">Course</router-link></li>
            <li><router-link to="/about">Faqs</router-link></li>
        </ul>
        <button class="cta">Join Us</button>
    </nav>
</template> -->
<template>
  <nav>
    <h1>G-learn</h1>

    
    <!-- Container for Links -->
    <div  class="nav-container" :class="{ open: navOpen }" >
      <ul>
        <li><a href="/" @click="closeNav">Home</a></li>
        <li><a href="/about" @click="closeNav">About</a></li>
        <li><a href="/courses" @click="closeNav">Courses</a></li>
        <li><a href="/faqs" @click="closeNav">Faqs</a></li>
      </ul>
      <button class="cta" @click="joinUs">Join Us</button>
    </div>
    <!-- Hamburger Icon -->
    <div
      @click="toggleNav"
      class="hamburger"
      :class="{ active: navOpen }"
    >
      <span></span>
      <span></span>
      <span></span>
    </div>
  </nav>
</template>


<script>
export default {
  name: "Navbar",
  data() {
    return {
      navOpen: false,
    };
  },
  methods: {
    toggleNav() {
      this.navOpen = !this.navOpen;
    },
    closeNav() {
      this.navOpen = false;
    },
    joinUs() {
      // Your join us logic
    }
  }
};
</script>

<style scoped>

nav {
  display: flex;
  font-family: "Poppins", sans-serif;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
  background-color: #fff;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  margin-bottom: 60px;
}

nav h1 {
  font-size: 2rem;
  font-weight: 700;
  color: #333;
}

.nav-container{
  display: flex;
  padding: 0 20px;
  justify-content: space-between;
}

nav ul {
  padding: 0 20px;
  display: flex;
  list-style: none;
  justify-content: space-around;
}

nav ul li {
  cursor: pointer;
  margin-left: 2rem;
}

/* nav ul li router-link {
  text-decoration: none;
  font-size: 25px;
  font-weight: 500;
  color: #333;
}

nav ul li a:hover {
  color: #000;
} */


nav ul li :deep(a) {
  text-decoration: none;
  font-size: 25px;
  font-weight: 500;
  color: #333;
}

nav ul li :deep(a:hover) {
  color: #000;
}
nav .cta {
  padding: 15px 30px;
  border: none;
  border-radius: 5px;
  background-color: #333;
  color: #fff;
  font-size: 1rem;
  font-weight: 500;
  cursor: pointer;
}

nav .cta:hover {
  transition: all 0.3s ease-in-out;
  background-color: #000;
}


/* General styles for the hamburger menu */
.hamburger {
  display: none; /* Initial hide on larger screens */
  cursor: pointer;
  flex-direction: column;
  justify-content: space-around;
  width: 30px;
  height: 25px;
}

.hamburger span {
  display: block;
  height: 3px;
  margin: 10px;
  width: 35px;
  background-color: #333;
  border-radius: 10px;
  transition: all 0.3s ease;
}

/* Media query for smaller screens */
@media only screen and (max-width: 768px) {
  .hamburger {
    display: block; /* Show on smaller screens */
    margin-right: 10px;
  }

  .hamburger.active span:nth-child(1) {
    transform: translateY(11px) rotate(45deg);
  }

  .hamburger.active span:nth-child(2) {
    opacity: 0;
  }

  .hamburger.active span:nth-child(3) {
    transform: translateY(-11px) rotate(-45deg);
  }

  /* Styles for the navigation container on smaller screens */
  .nav-container{
    position: absolute;
    left: -120%;
    /* left:0; */
    top: 75px;
    gap: 0;
    /* padding: 20px; */
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    /* margin: 15%  10px; */
    margin: 70px 10px  70px 25px;
    padding: 10px;
    width: 80%;
    color: #fff !important;
    background-color: #fff;
    border: 2px #333 solid;
    text-align: center;
    transition: 0.3s;
  }
  .nav-container ul {
    /* ... other styles ... */
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
    padding: 20px;
    list-style: none; /* Removes default list styling */
  }

  .nav-container ul li {
    margin: 10px 0; /* Adjust as needed for spacing */
  }
  .nav-container.open {
    left:0;
  }

  .cta{
    width: 100%;
  }
}


</style>