<script setup>

import {ref} from 'vue'

const header = ref('Furniture Pro Ltd')

const name = ref('')
const email = ref('')
const message = ref('')
const submitted = ref(false)

const submitForm = ()=>{
    submitted.value = true;
}

</script>

<template>
    <div id="navbar">
        <div class="navbarItems">
            <p>Home</p>
            <p>Bio</p>
            <p>My Creations</p>
            <p>Contact</p>
        </div>
    </div>

    <hr>
    <div class="scroller">
      <section id="home">
          <div>
              <h2 class="title part1">{{ header }}</h2> 
          </div>
          <br><br><br><br><br><br>
                            
        <div class="openingWords">
            <p>In this modern era, where the world is turning to aluminium based furnitures</p>
            <br>
            <p> We offer the best quality wooden decor, cabinetry, table and fitment while guaranteeing the cheapest price</p>
            <br>
            <p>Our goal is to make your vision a reality and scale your business onto the internet.</p>
        </div>
      </section>
      
      <section id="subscribe">
        <br>
        <br>
        <h1>Subscribe to this website.</h1>
        <p class="subscribedtext">Before leaving this website, it would be great if you could leave a comment below and subscribe to our website to receive latest deals and to check out the newest furniture pro creations</p>
        <form class="subscribetext" @submit.prevent="submitForm">
            <label for="name">Name:</label>
            <input type="text" id="name" v-model="name" required><br><br>

            <label for="email">Email:</label><br>
            <input type="email" id="email" v-model="email" required><br><br>

            <label for="message">Message:</label><br>
            <textarea id="message" v-model="message" row="4" cols="50" required></textarea><br><br>

            <label for="subscribe">Subscribe to Website:</label>
            <input type="checkbox" id="subscribe" v-model="subscribe"><br><br>

            <button class="btn btn-primary" type="submit">Submit</button>
        </form>

        <div v-if="submitted">
            <h2>Submitted Data:</h2>
            <p><strong>Name:</strong> {{ name }}</p>
            <p><strong>Email:</strong> {{ email }}</p>
            <p><strong>Message:</strong> {{ message }}</p>
            <p><strong>Subscribed:</strong> {{ subscribe ? 'Yes' : 'No' }}</p>
        </div>
        
      </section>
  
      <section id="myCreations">
  
      </section>
      
    </div>

</template>
