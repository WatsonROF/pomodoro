<template>
    <div> 
        <el-button @click="$emit('iniciarIntervalo')">Começar Intervalo</el-button>
    </div> 
</template>

<script>

export default {
    name: "ButtonIntervalo",
    emits: ["iniciarIntervalo"]
}
</script>
