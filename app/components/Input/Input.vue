<template>
    <div>
        <InputLabel class="mb-1"><slot/></InputLabel>
        <InputField :input-type="inputType" />
    </div>
</template>

<script setup>
    const props = defineProps(["inputType"])
</script>

<style lang="scss" scoped>

</style>