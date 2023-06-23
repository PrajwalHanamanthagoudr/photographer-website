<template>
  <v-app id="home">
    <NavigationMenu />
    <v-main>
      <section class="relative flex items-center justify-center overflow-hidden min-h-120 flex-none" id="home"
        style="background-image: url('https://images.unsplash.com/photo-1527888477750-6fd34fbfa3f0?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1171&q=80'); background-position: center center; background-size: cover;">
        <div class="w-full h-full absolute top-0 left-0" style="background-color: rgba(61, 64, 91, 0.5);"></div>
        <div class="relative container mx-auto px-6 z-10 py-12 lg:py-32 xl:py-40">
          <div class="max-w-3xl text-center mx-auto"><br><br><br><br><br>
            <h2 class="heading-xlarge  mb-6 break-word text-center"
              style="color: rgb(0, 0, 0); font-size: 4rem; font-family: var(--head-fontFamily); font-weight: var(--head-fontWeight);">
              Capture Life's Moments Beautifully</h2>
            <p class="body-large text-white text-h6" style="scroll-behavior: smooth;">
              Experience the art of photography with Mallu's professional services. Perfect for weddings, corporate
              events,
              family portraits, landscapes, and more!</p><br><br><br><br>
          </div><br><br><br><br><br><br><br>
        </div>
      </section>
      <section class="bg-black" id="gallery">
        <h1 class="text-h4 px-8 py-6 text-decoration-overline text-white font-bold">Our Work</h1>
        <v-container>
          <div class="d-flex bg-white">
            <v-img class="ma-2 pa-5" style="width: 4%;" src="@/assets/background6.jpg"></v-img>
            <v-img class="ma-2 pa-5" style="width: 4%;" src="@/assets/background2.jpg"></v-img>
          </div>
          <div class="d-flex flex-row mb-6 bg-white">
            <v-img class="ma-2 pa-5" style="width: 4%;" src="@/assets/background8.jpg"></v-img>
            <v-img class="ma-2 pa-5" style="width: 4%;" src="@/assets/background.jpg"></v-img>
          </div>
        </v-container>
        <br>
        <br>
      </section>
      <v-container id="about">
        <h1 class="text-h4 mb-6 text-center pt-15 text-decoration-overline font-bold">About Us</h1>
        <div class="flex justify-center">
          <div class="w-2/3">
            <p class="text-h7 pl-16 pr-16 pb-16 text-center"
              style="line-height: 2.4rem; letter-spacing: 0.08rem; word-spacing: 0.09rem; text-align: center;">
              <span class="text-decoration-underline">Mallu The Photographer</span> is a Gadag-based photography business
              that specializes in capturing the essence of life's
              most
              precious moments.
              Our team of talented photographers is dedicated to providing you with high-quality, stunning images that
              will
              last a lifetime.
              <br>
              Whether you're looking for a wedding photographer or simply need a portrait session,
              Mallikarjun has the expertise and experience to deliver exceptional results.
              We pride ourselves on our attention to detail and commitment to customer satisfaction,
              and we strive to exceed your expectations with every shoot.
              Contact us today to learn more about our services and to schedule your session.
            </p>
          </div>
        </div>
      </v-container>
      <section style="background-color:rgb(240, 240, 240);" id="services">
        <h1 class="text-h4 mb-6 text-center pt-15 text-decoration-overline" style="font-weight: bold;">Our Services</h1>
        <div class="d-flex flex-wrap ma-10 justify-center">
          <div v-for="card in cards" :key="card.id" class="pa-10">
            <va-card stripe :stripe-color=card.color textColor="#424242" style="width: 18rem;">
              <va-card-title text-color="#000000" class="text-h6 justify-center">{{ card.title }}</va-card-title>
              <va-image :src="card.imageSrc" style="width: 100%; height: 20rem;">
                <va-card-title text-color="#fff">{{ card.title }}</va-card-title>
              </va-image>
              <va-card-content>{{ card.content }}</va-card-content>
            </va-card>
          </div>
        </div>
        <center> <v-btn color="black" class="mb-5"> And More...</v-btn></center>
      </section><br>
      <section id="testimonials">
        <center class="text-h4 text-center text-decoration-overline pb-10">Testimonials</center>
        <v-carousel cycle hide-delimiters style="height: 25rem; background-color: rgb(0, 0, 0);">
          <v-carousel-item v-for="(item, index) in testimonials" :key="index" class="text-center pt-16 mb-16">
            <v-card-text class="pa-14 justify-center"
              style="letter-spacing: 0.1rem; word-spacing: 0.2rem; font-size: large; font-weight: lighter;">
              <h3 class="text-center text-white">{{ item.text }}</h3>
              <p class="text-center text-white mt-5 flex justify-center items-center">{{ item.author }}</p>
            </v-card-text>
          </v-carousel-item>
        </v-carousel>
      </section>
      <LocationPage />
      <section style="background-color:rgb(240, 240, 240)" id="contact">
        <v-container class="py-8 lg:py-12 xl:py-16">
          <h1 class="text-center text-decoration-overline text-h4 pt-5">Contact Us</h1>
          <v-row class="flex-wrap flex-row-reverse mt-10 mb-10">
            <v-col cols="12" md="6" class="mt-10">
              <div class="rich-text-block">
                <h3 class="mb-3" style="font-size: 1.7rem; font-weight: lighter;">Get in Touch with Us</h3>
                <p style="font-size: 1.3rem; letter-spacing: 0.09rem; line-height: 2rem; color: #484848;">Have a
                  question or
                  interested in our photography services? Fill out the form below
                  and we'll get back to you as soon as possible. We can't wait to hear from you!</p>
              </div>
            </v-col>

            <v-col cols="12" sm="6">
              <v-form>
                <v-container>
                  <v-row>
                    <v-col cols="12" sm="6" md="6">
                      <v-text-field label="Name" v-model="name" placeholder="Enter Your Name"
                        variant="outlined"></v-text-field>
                    </v-col>

                    <v-col cols="12" sm="6" md="6">
                      <v-text-field label="Email" v-model="email" placeholder="Enter Your Email"
                        variant="outlined"></v-text-field>
                    </v-col>

                    <v-col cols="12" sm="12" md="16">
                      <v-textarea label="Message" v-model="message" auto-grow variant="outlined" rows="5" row-height="25"
                        shaped placeholder="Write Your Message..."></v-textarea>

                    </v-col>
                    <v-row class="mr-3">
                      <v-btn class="ml-auto send" color="black" rounded="l" @click="submit()">Send</v-btn>
                    </v-row>
                  </v-row>
                </v-container>
              </v-form>
            </v-col>
          </v-row>
          <v-dialog v-model="dialog" transition="dialog-top-transition" width="350" height="250">
            <v-card>
              <v-toolbar :color="dialogColor" :title="dialogTitle"></v-toolbar>
            </v-card>
          </v-dialog>
        </v-container>
        <FooterPage />
      </section>
    </v-main>
  </v-app>
</template>

<script>
import { defineComponent } from 'vue';
import NavigationMenu from '@/components/NavigationMenu.vue';
import LocationPage from '@/components/LocationPage.vue'
import FooterPage from '@/components/FooterPage.vue';

export default defineComponent({
  name: 'HomeView',
  components: {
    NavigationMenu,
    LocationPage,
    FooterPage,
  },
  data: () => ({
    name: '',
    email: '',
    message: '',
    dialog: false,
    dialogTitle: '',
    dialogColor: '',
    cards: [
      {
        id: 1,
        imageSrc: 'https://hdwallpaperim.com/wp-content/uploads/2017/09/17/61905-photography-camera-748x468.jpg',
        color: '#2196F3',
        title: 'Product Photography',
        content: "We capture high-quality images of your products that not only showcase their features but also entice customers to make a purchase."
      },
      {
        id: 2,
        imageSrc: 'https://img.freepik.com/free-photo/shine-wedding-altar-newlyweds-stands-backyard-decorated-with-balloons_8353-8415.jpg?size=626&ext=jpg&ga=GA1.2.1453379349.1679546840&semt=ais',
        title: 'Event Photography',
        color: '#E91E63',
        content: 'Whether its a corporate event or a wedding, our photographers will capture every moment, and delivering stunning images that tell your story.',
      },
      {
        id: 3,
        imageSrc: 'https://images.pexels.com/photos/1787235/pexels-photo-1787235.jpeg?cs=srgb&dl=pexels-luis-quintero-1787235.jpg&fm=jpg',
        title: 'Portrait Photography',
        color: '#FFEA00',
        content: 'We create timeless portraits that capture your personality and convey your message. Our photographers work with you to create a unique visual narrative.',
      },
    ],
    testimonials: [
      {
        text: "Mallu's photography skills are exceptional! The attention to detail and creativity in each shot is truly impressive. I highly recommend him for any photography needs in Bengaluru. Thank you for capturing such beautiful memories!",
        author: "- Nanda",
      },
      {
        text: "Mallu's photography skills are top-notch! He captured the essence of my event beautifully. He was professional, punctual, and his attention to detail was impressive. Thank you for making my special day even more memorable with your stunning photographs.",
        author: "- Madhu",
      },
      {
        text: "mallu is an amazing photographer! His attention to detail and creativity are unparalleled. He captured the essence of my event perfectly and delivered the photos promptly. Highly recommend his services to anyone looking for beautiful photos!",
        author: "- Prashanth",
      },
    ],
  }),
  methods: {
    submit() {
      if (this.name && this.email && this.message) {
        this.dialogTitle = 'Message sent successfully...!';
        this.dialogColor = 'green';
        this.name = '';
        this.email = '';
        this.message = '';
      } else {
        this.dialogTitle = 'Enter required fields...!';
        this.dialogColor = 'red';
      }
      this.dialog = true;
    }
  }
});
</script>
