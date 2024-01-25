<template>
  <!-- <div> -->
  <Navbar />

  <div class="main-container">
    <div class="container">
      <div class="home__content">
        <h1 class="home__title">
          Empower Your Learning Journey with Glearn
        </h1>
        <p class="home__description">
          Interactive, Engaging, and Tailored Online
          Education for All Ages
        </p>
        <img
          class="arrow"
          src="./assets/curved-arrow-png-free-download (1).png"
          alt=""
          srcset=""
        />
        <div class="btncont">
          <button class="home__cta">Join Waitlist</button>
          <button class="home__cta">
            Explore Course &LongRightArrow;
          </button>
        </div>
      </div>
      <img
        class="homeimg"
        src="./assets/pexels5.jpg"
        alt=""
      />
      <!-- </div> -->
    </div>

    <section class="second">
      <h2>Achieve Your Goals with G-learn</h2>

      <div class="card__container">
        <div class="card" v-for="content in cardcontent">
          <img
            v-bind:src="content.img"
            style="width: 200px; height: 200px"
            alt=""
          />
          <h3>{{ content.title }}</h3>
          <p>{{ content.description }}</p>
        </div>
      </div>
    </section>

    <section class="third">
      <div class="thirds">
        <h2>Our Courses</h2>
        <p>
          Meet Professionals with Real life experience in
          teh tech industry
        </p>
      </div>

      <div class="second__card-container">
        <div class="second__card">
          <div
            class="cards"
            v-for="course in courseContent"
          >
            <img v-bind:src="course.image" alt="" />
            <div class="des">
              <h3>{{ course.title }}</h3>
              <p>{{ course.tutor }}</p>
              <div>
                <span>&star;</span>
                <span>&star;</span>
                <span>&star;</span>
                <span>&star;</span>
                <span>&star;</span>
              </div>
              <button>{{ course.button }}</button>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="accordion__container">
      <h1>FAQ</h1>
      <div class="accordion">
        <h2 class="accordion__title">
          Frequently Asked Questions
        </h2>

        <div
          class="content__container"
          v-for="(item, index) in faqs"
          :key="index"
        >
          <div class="questions" @click="toggle(index)">
            {{ item.question }}
          </div>
          <div
            class="answers"
            v-show="activeIndex === index"
          >
            {{ item.answer }}
          </div>
        </div>
      </div>
    </section>
    <Waitlist />
    <Footer />
    <!-- </div> -->
    
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import careerImg from "./assets/career.png";
import powerImg from "./assets/power.png";
import medalImg from "./assets/medal.png";
import publicImg from "./assets/pexels3.jpg";
import Waitlist from "./components/Waitlist.vue";
import Footer from "./components/Footer.vue";
// import imgage from './assets/pexels-julia-m-cameron-4144923.jpg'/

export default {
  name: "Home",
  components: {
    Navbar,
    Waitlist,
    Footer
},

  data() {
    return {
      cardcontent: [
        {
          title: "Advance Your Career",
          description:
            "Hone your skills with comprehensive online courses and be one step closer to your dream job.",
          img: careerImg,
        },
        {
          title: "Build Your Business",
          description:
            "Learn how to grow your business with step-by-step guidance from top experts in the industry.",
          img: powerImg,
        },
        {
          title: "Get certified",
          description:
            "Earn industry-recognized credentials that showcase your skills to recruiters and hiring managers.",
          img: medalImg,
        },
      ],

      courseContent: [
        {
          image: publicImg,
          title: "Introduction to public speaking",
          tutor: "The net Ninja",
          button: "Preview",
        },
        {
          image: publicImg,
          title: "Introduction to public speaking",
          tutor: "The net Ninja",
          button: "Preview",
        },
        {
          image: publicImg,
          title: "Introduction to public speaking",
          tutor: "The net Ninja",
          button: "Preview",
        },
        // {
        //   image: publicImg,
        //   title: "Introduction to public speaking",
        //   tutor: "The net Ninja",
        //   button: "Preview",
        // },
      ],

      activeIndex: null, // Keeps track of the currently active accordion item
      faqs: [
        {
          question: "How do I pay for courses?",
          answer:
            "Lorem ipsum dolor sit amet consectetur...",
        },
        {
          question: "What is the refund policy?",
          answer:
            "Lorem ipsum dolor sit amet consectetur...",
        },
        {
          question: "How long are the courses?",
          answer:
            "Lorem ipsum dolor sit amet consectetur...",
        },
        // ... add more FAQs as needed
      ],
    };
  },

  methods: {
    toggle(index) {
      this.activeIndex = this.activeIndex === index ? null : index;

      console.log("Active Index:", this.activeIndex); // Debugging line
    },
  },
};
</script>

<style scoped>
.main-container {
  font-family: "Lato", sans-serif;
}
.container {
  /* max-width: 1200px; */

  margin: 0 auto;
  display: flex;
  /* padding: 0 2rem; */
  justify-content: space-around;
  align-items: center;
}

.homeimg {
  /* width: 100%; */
  height: 500px;
  width: 650px;
 border-radius: 50px;
  object-fit: cover;
}

.home__content {
  width: 50%;
}

.home__title {
  font-size: 4rem !important;
  /* font-weight: 700; */
  color: #333;
  margin-bottom: 1rem;
}

.arrow {
  height: 100px;
  margin-left: 50px;
}
.home__description {
  font-size: 1.5rem !important;
  font-weight: 500;
  color: #333;
  margin-bottom: 2rem;
}

.home__cta {
  padding: 1rem !important;
  border: none;
  border-radius: 5px;
  background-color: #333;
  color: #fff;
  font-size: 25px !important;
  /* font-weight: 500; */
  cursor: pointer;
  margin-right: 1rem;
}

.home__cta:hover {
  background-color: #000;
}

.home__img {
  width: 700px;
  height: 100%;
  object-fit: cover;
}

.btncont {
  display: flex;
  flex-direction: row;
}

.second {
  margin-top: 150px;
  margin-bottom: 100px;
}

.second h2 {
  text-align: center;
  margin-bottom: 50px;
  font-size: 2.5rem;
}

.card__container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  align-items: center;
  width: 100%; /* Adjust as needed */
}

.card {
  cursor: pointer;
  width: 350px;
  height: 450px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 0 20px;
  font-size: 20px;
  text-align: center;
  border-radius: 20px;
  box-shadow: 2px 4px 5px #333;
}

.card:hover {
  color: lightgrey;
  background-color: #333;
  transition: all 0.5s ease-in-out;
}

.second__card {
  justify-content: space-around;
  display: flex;
}

.thirds {
  text-align: center;
  margin: 5%;
}

.thirds h2 {
  font-size: 2.5rem;
}

.thirds p {
  font-size: 25px;
}

.cards {
  width: 400px;
  height: 550px;
  font-size: 20px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.12), 0 6px 20px rgba(0, 0, 0, 0.08);
  transition: box-shadow 0.3s ease-in-out;
  /* border-radius:30px ; */
}

.cards:hover{
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.16), 0 12px 40px rgba(0, 0, 0, 0.12);
  }

.cards img {
  width: 100%;

  /* border-radius:30px ; */
  /* height: 25; */
}

.des {
  padding: 20px;
}

span {
  color: black;
  /* background-color: yellow; */
  font-size: 30px;
}

.des button {
  padding: 15px 30px;
  outline: none;
  font-size: 25px;
  background-color: #575555;
  color: white;
  border: none;
  cursor: pointer;
  width: 100%;
  margin-top: 20px;
  border-radius: 5px;
}

.des button:hover {
  transition: all 0.5s ease-in-out;
  background-color: #333;
}

.des p {
  color: #575555;
}

.accordion__container {
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  margin-top: 10%;
}

.accordion__container h1 {
  font-size: 2.5rem;
}

.accordion {
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.16), 0 12px 40px rgba(0, 0, 0, 0.12);
  width: 85%;
  background-color: #fff;
  color:black;
  padding: 40px;
  border-radius: 30px;
}

.accordion .accordion__title {
  font-size: 2rem;
  text-align: center;
  margin-bottom: 30px;
}

.accordion .content__container .questions {
  padding: 18px 0px;
  font-size: 25px;
  /* color: white; */
  cursor: pointer;
  position: relative;
  border-bottom: 1px solid #575555;
}

.accordion .content__container .questions::after {
  content: "+";
  position: absolute;
  right: -5px;
  font-size: larger;
}

.answers {
  /* display: none; */
  padding-top: 15px;
  font-size: 22px;
  line-height: 1.5;
  width: 100%;
  overflow: hidden;
  height: auto;
  transition: height 0.5s ;
}

.answers--visible {
  display: block;
  max-height: 500px; /* Adjust as needed */
}



/* Responsive styles using media queries */
@media only screen and (max-width: 1200px) {
  .container {
    flex-direction: column;
  }
/* 
  .homeimg {
    width: 100%;
    border-radius: 0;
    margin-bottom: 20px;
  } */

  .home__content {
    width: 80%;
  }

  /* ... (adjust other styles as needed) ... */
}

@media only screen and (max-width: 768px) {
  .home__title {
    font-size: 3rem;
  }

  .home__description {
    font-size: 1.2rem !important;
  }

  .btncont {
    flex-direction: column;
  }

  .home__cta {
    margin-bottom: 10px;
  }

  .homeimg{
    border-radius: 30px;
    width: 350px;
    height: 400px;
    object-fit: cover;
  }

  .second h2 {
    font-size: 2rem;
  }

  .second__card{
    flex-direction: column;
    align-items: center;
  }



  .card {
    width: 300px;
    margin-bottom: 40px;
  }

  .thirds h2 {
    font-size: 2rem;
  }

  .thirds p {
    font-size: 1rem;
  }

  .cards {
    width: 350px;
    height: auto;
    margin-bottom: 20px;
  }
  
  .accordion {
    padding: 20px;
  }

  .accordion .accordion__title {
    font-size: 1.8rem;
    margin-bottom: 20px;
  }

  .accordion .content__container .questions {
    font-size: 20px;
  }

  .answers {
    font-size: 18px;
  }
}
</style>
