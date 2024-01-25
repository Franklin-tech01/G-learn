<template>
  <div class="waitlist-container">
    <h2>Join Our Waitlist</h2>
    <form @submit.prevent="submitForm">
      <div class="form__container">
        <div class="form-group">
          <!-- <label for="fullName">Full Name:</label> -->
          <input
            type="text"
            id="fullName"
            v-model="fullName"
            required
          />

          <!-- <div class="form-group"> -->
          <!-- <label for="email">Email:</label> -->
          <input
            class="distinct"
            type="email"
            id="email"
            v-model="email"
            placeholder="Enter your email"
            required
          />
        </div>
        <!-- </div> -->
        <button type="submit">Join Waitlist</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      fullName: "",
      email: "",
    };
  },
  methods: {
    submitForm() {
      // You can handle form submission logic here
      console.log(
        "Form submitted:",
        this.fullName,
        this.email
      );
    },
  },
};
</script>

<style scoped>

h2 {
  text-align: center;
  font-size: 2rem;
  margin-bottom: 20px;
}

.waitlist-container{
  margin-top: 5%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.form-group {
  /* margin-bottom: 15px;
  margin-top: 20px;
  padding: 20px;
  border-radius: 20px;
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.16), 0 12px 40px rgba(0, 0, 0, 0.12); */
  display: flex;
}

.form__container{
  margin-top: 20px;
  padding: 20px;
  border-radius: 20px;
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.16), 0 12px 40px rgba(0, 0, 0, 0.12);
  /* display: flex; */
}

label {
  display: block;
  font-size: 25px;
  margin-bottom: 5px;
}

input {
  width: 450px;
  font-size: 25px;
  padding: 8px;
  height: 50px;
  border: none;
  /* border:  2px silver solid; */
  /* border-radius: 4px; */
  margin: 10px 2px;
  color: #282525;
  box-sizing: border-box;
  outline: none;
}

.distinct{

  border-left: 2px solid #333;
}

button {
  background-color: #201e1e;
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 15px 30px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 20px;
}

button:hover {
  background-color: #333;
  transition: 0.5s ease-out;
}


@media only screen and (max-width: 768px){

.form-group{
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  justify-content: center;
}

input{
   border:  2px silver solid;
   border-radius: 10px;
   width: 320px;
   font-size: small;
}


button{
  width: 100%;
}

form{
  width: 350px;
}

}
</style>
