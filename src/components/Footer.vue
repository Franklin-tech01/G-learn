<template>
  <footer class="footer">
    <div class="container">
      <div class="footer-content">
        <div class="about">
          <h3>About Us</h3>
          <p>
            Leading the future of education with innovative
            technology solutions.
          </p>
        </div>
        <div class="links">
          <h3>Quick Links</h3>
          <ul>
            <li><a href="/about">About</a></li>
            <li><a href="/courses">Courses</a></li>
            <li><a href="/contact">Contact Us</a></li>
            <li><a href="/faq">FAQ</a></li>
          </ul>
        </div>
        <div class="contact">
          <h3>Contact</h3>
          <p>Email: info@edtech.com</p>
          <p>Phone: +123 456 7890</p>
        </div>
        <div class="social-media">
          <h3>Follow Us</h3>
          <div class="social-icons">
            <a href="#"
              ><ion-icon name="logo-facebook"></ion-icon
            ></a>
            <a href="#"
              ><ion-icon name="logo-twitter"></ion-icon
            ></a>
            <a href="#"
              ><ion-icon name="logo-linkedin"></ion-icon
            ></a>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: "FooterComponent",
  // Add your JavaScript logic here if needed
};
</script>

<style scoped>
.footer {
  background-color: #333;
  color: lightgray;
  padding: 40px 0;
  margin-top: 50px;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 15px;
  display: flex;
  justify-content: space-between;
}

.footer-content div {
  flex-basis: 20%;
}

.footer h3 {
  margin-bottom: 15px;
  color: #fff;
}

.footer ul {
  list-style: none;
  padding: 0;
}

.footer ul li a {
  color: lightgray;
  text-decoration: none;
}

.footer ul li a:hover {
  color: #fff;
}

.social-icons {
  display: flex;
  gap: 10px;
}

.social-icons ion-icon {
  width: 50px; /* Adjust size as needed */
  font-size: 40px;
  color: white;
}



/* Responsive design adjustments */
@media (max-width: 768px) {
  .container {
    flex-direction: column;
    align-items: center;
  }

  .footer-content div {
    margin-bottom: 20px;
  }
}
</style>
