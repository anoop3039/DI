<template>
    <div id="BlogPage">
        <CommonBridgeSection :text="BridgeText" center="true"  />
        <BlogBCard />
    </div>
</template>
<script>

export default {
    data() {
        return {
            BridgeText: 'Blog'
        }
    },
}

</script>