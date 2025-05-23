<script setup>


const dataFromParent = defineProps(
    ['firstName',
    'lastName'
    ]
);



</script>


<template>
    
    <div>
        <h1>{{ dataFromParent.firstName }}</h1>
        <h1>{{ dataFromParent.lastName }}</h1>
    </div>

</template>