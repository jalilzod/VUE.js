<script setup>

    import {computed,ref} from 'vue';


    const firstName = ref('Ming');
    const lastName = ref('Yuan');
    
    const fullName = computed(()=>{
        return firstName.value+' '+lastName.value;
    });


</script>


<template>
    <div>
        <h1>First Name: {{ firstName }}</h1>
        <h1>Last Name: {{ lastName }}</h1>
        <h1>Fullname:{{ fullName }} </h1>
    </div>
</template>