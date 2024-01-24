<template>
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
</template>
<script>


export default {
    name: 'Navbar'
}

</script>

<style scoped>
    nav {
        display: flex;
        font-family: 'Poppins', sans-serif;
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

    nav ul {
        display: flex;
        list-style: none;
    }

    nav ul li {
        cursor: pointer;
        margin-left: 2rem;
    }

    nav ul li router-link{

        text-decoration: none;
        font-size:25px;
        font-weight: 500;
        color: #333;
    }

    nav ul li a:hover {
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

    
@media only screen and (max-width: 768px) {
    nav{
        display: none;
    }
}
</style>