<template>
    <div id="PortfolioPage">
        <CommonBridgeSection :text="BridgeText" center="true"  />
        <PortfolioImageText />
    </div>
</template>
<script>

export default {
    data() {
        return {
            BridgeText: 'Portfolio'
        }
    },
}

</script>