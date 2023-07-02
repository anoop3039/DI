<template>
    <div id="services-page">
        <CommonBridgeSection :text="BridgeText" center="true"  />
        <ServicesBetterSection />
        <ServicesMainSection />
    </div>
</template>
<script>

export default {
    data() {
        return {
            BridgeText: 'Digital Marketing Services'
        }
    },
}

</script>