<template>
    <HomeHeroSection />
    <HomeCarouselSection />
    <HomeHowToGrowSection />
    <CommonBridgeSection :text="BridgeText" />
    <HomeVariousServicesSection />
    <HomeWhyWeBest />
    <HomeContactSection />
    <HomeTestimonialSection />
</template>

<script>
import { onMounted } from 'vue';
import AOS from 'aos';
import 'aos/dist/aos.css';
export default {
    data() {
        return {
            BridgeText: 'Let us build the bridge between your brand and customer'
        }
    },
    setup() {
        onMounted(() => {
        AOS.init({
            once: true,
        });
        });
    },
}
</script>