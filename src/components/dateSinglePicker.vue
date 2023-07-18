<template>
    <div>
        <v-text-field
            v-model="dateValue"
            label="日期"
            variant="outlined"
            density="compact"
            class="w-300 d-inline-block"
            color="blue-darken-1"
            clearable
            persistent-placeholder
            hide-details
            readonly
            @click="showDatePicker = true"
        ></v-text-field>
        <v-date-picker
            v-if="showDatePicker"
            class="mx-auto"
            color="primary" 
            v-model="date"
            hide-actions
            show-adjacent-months
            position="absolute"
        >
        </v-date-picker>
    </div>
</template>
<script setup>
import { ref,reactive, watch} from 'vue';
import { VDatePicker } from 'vuetify/labs/VDatePicker'

const date = ref('');
const dateValue = ref('');
const showDatePicker = ref(false);

watch(() => date.value, () => {
    // dateValue.value = date.value ? `${(new Date(date.value)).getFullYear()}-${(new Date(date.value)).getMonth()+1}-${(new Date(date.value)).getDate()}` : '';
    // showDatePicker.value = dateValue.value != '' ? false : true;
    console.log(date.value)
})

// watch(()=> dateValue.value, () => {
//     if(!dateValue.value){
//         date.value = '';
//     }
// })

</script>

<style lang="scss" scoped>
    :deep(.v-picker-title){
        display: none;
    }
    :deep(.v-picker__header){
        display: none;
    }

</style>