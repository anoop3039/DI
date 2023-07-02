<template>
    <div id="ContactPage">
        <CommonBridgeSection :text="BridgeText" center="true"  />\
        <ContactUsFormSection />
    </div>
</template>
<script>

export default {
    data() {
        return {
            BridgeText: 'Contact Us'
        }
    },
}

</script>