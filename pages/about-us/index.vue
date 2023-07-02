<template>
    <div id="about-us-page">
        <CommonBridgeSection :text="BridgeText" center="true"  />
        <AboutUsBussinessSection />
        <AboutUsServicesSection />
        <AboutUsComprehensiveSection />
        <AboutUsOurMissionSection />
    </div>
</template>
<script>

export default {
    data() {
        return {
            BridgeText: 'About Us'
        }
    },
}

</script>