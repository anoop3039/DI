<template>
    <div>
      <nav class="bg-gray-900 w-full z-20 top-0 left-0 border-b border-gray-200 border-gray-600 relative" ref="navbar">
        <div class="container px-4 flex flex-wrap items-center justify-between mx-auto py-7">
          <NuxtLink to="/" class="flex items-center">
            <img src="https://flowbite.com/docs/images/logo.svg" class="h-8 mr-3" alt="Flowbite Logo">
            <span class="self-center text-2xl font-semibold whitespace-nowrap text-white">Digital Intelligence</span>
          </NuxtLink>
        
          <div 
            class="items-center justify-between hidden w-full lg:flex lg:w-auto bg-gray-900" 
            :class="[nav ? 'show' : 'hide']" id="navbar-sticky" ref="listLinks">
            <ul class="flex flex-col p-4 lg:p-0 mt-4 font-medium border border-gray-100 rounded-lg bg-gray-50 lg:flex-row lg:space-x-8 lg:mt-0 lg:border-0 bg-gray-900 md:bg-gray-900 border-gray-700 mt-0" >
              <li v-for="navlink in navLinks" :key="navlink.name"  class="relative"   >
                <NuxtLink
                  :to="navlink.link"
                  class="block py-2 pl-3 pr-4 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:hover:text-blue-700 lg:p-0 md:hover:text-blue-500 text-white hover:bg-gray-700 hover:text-white md:hover:bg-transparent border-gray-700"
                  @click="handleToggle(navlink)"
                  v-if="navlink.name !== 'Services'"
                >
                  {{ navlink.name }}
                </NuxtLink>
                <span
                  class="block py-2 pl-3 pr-4 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:hover:text-blue-700 lg:p-0 md:hover:text-blue-500 text-white hover:bg-gray-700 hover:text-white md:hover:bg-transparent border-gray-700 cursor-pointer"
                  @click="handleClick(navlink)"
                  v-else
                  :class="serviceActive ? 'router-link-active' : ''"
                >
                  {{ navlink.name }}
                </span>
                <div v-if="navlink.name === 'Services'" v-show="showServices"  class="md:absolute left-0 md:mt-10 md:w-64 bg-white rounded-lg shadow-lg">
                  <ul class="py-5 bg-white-900 " ref="singleService" @click="toggleNav" >
                    <li v-for="service in services" :key="service.name"  class="">
                      <NuxtLink
                        :to="service.link"
                        class="block px-4 py-2 text-gray-900"
                        aria-current="page"
                        @click="toggleServices"
                      >
                        {{ service.name }}
                      </NuxtLink>
                    </li>
                  </ul>
                </div>
              </li>
            </ul>
          </div>
  
          <div class="flex">
            <NuxtLink to="contact-us" class="custom-get-started text-white bg-blue-500 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg px-4 py-2 text-center mr-3 md:mr-0 bg-blue-600 hover:bg-blue-700 focus:ring-blue-800 hidden md:block">Get started</NuxtLink>
            <button @click="toggleNav" class="inline-flex items-center p-2 text-sm text-gray-500 rounded-lg lg:hidden hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-gray-200 text-gray-400 hover:bg-gray-700 focus:ring-gray-600 ml-5">
              <span class="sr-only">Open main menu</span>
              <nuxt-icon name="hamburger" />
            </button>
          </div>
        </div>
      </nav>  
    </div>
  </template>
  
<script>

export default {
    data() {
        return {
            navLinks: [
                {name: 'Home', link: '/'},
                {name: 'About Us', link: '/about-us'},
                {name: 'Services', link: '/services'},
                {name: 'Portfolio', link: '/portfolio'},
                {name: 'Blog', link: '/blog'},
                {name: 'Contact Us', link: '/contact-us'},
            ],
            services: [
                {name: 'All Services', link: '/services'},
                {name: 'Web Designing', link: '/services/web-designing'},
                {name: 'Web Development', link: '/services/web-development'},
                {name: 'Search Engine Optimization', link: '/services/search-engine-optimization'},
                {name: 'Social Media Marketing', link: '/services/social-media-marketing'},
                {name: 'Pay Per Click Management', link: '/services/pay-per-click-management'},
            ],
            nav: false,
            showServices: false,
            serviceActive: false,
        }
    },
    methods: {
        toggleNav(){
            this.nav = !this.nav;
        },
        toggleServices() {
            this.showServices = !this.showServices;
        },
        handleClick(navlink, event) {
            this.toggleServices();
            this.serviceActive = true;
        },
        handleToggle(navlink){
            console.log('clickedssss');
            this.nav = false
            this.showServices = false;
            this.serviceActive = false;
        },
        handleClickOutside(event) {
            const navbarElement = this.$refs.navbar ;

            // Check if the clicked element is outside the navbar and listLinks elements
            if (!navbarElement.contains(event.target)) {
                // Handle the click outside logic here
                this.nav = false
            }
        },
        // activeParentLink(){
        //     console.log('yes mounted');
        //     const activeLink = document.querySelector('a.router-link-active');
        //     if (activeLink) {
        //         const list = activeLink.closest('li').parentNode.parentNode.parentNode
        //         if(list){
        //             list.classList.add('router-link-active');
        //         }
        //     } 
        // }
        
            
    },

    mounted() {
        
    },
    beforeUnmount() {
        document.removeEventListener("click", this.handleClickOutside);
    },
 
}

</script>
<style scoped>

a.router-link-active.router-link-exact-active{
    color: rgb(59 130 246 / 1);
}
.router-link-active{
    color: rgb(59 130 246 / 1);
}
.custom-get-started {
    color: #fff !important;
}
@media only screen and (max-width: 1024px) {
    .show{
        display: block;
        position: absolute;
        top: 100%;
        z-index: 9;
        left: 0;
    }
}
</style>