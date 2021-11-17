<template>
    <div> 
        <el-button @click="$emit('iniciarTimer')">Começar Timer</el-button>
    </div> 
</template>

<script>

export default {
    name: "ButtonComecar",
    emits: ["iniciarTimer"]

}
</script>
