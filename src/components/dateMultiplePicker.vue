<template>
    <div>
        <v-text-field
            v-model="dateRange"
            label="日期區間"
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
            v-model="dates.value"
            multiple 
            hide-actions
            show-adjacent-months
            position="absolute"
        >
        </v-date-picker>
    </div>
</template>
<script setup>
import { ref,reactive, watch, computed} from 'vue';
import { VDatePicker } from 'vuetify/labs/VDatePicker'

const dates = reactive([]);
const dateRange = ref('');
const showDatePicker = ref(false);

watch(() => dates.value, () => {
    let startDate = dates.value[0] ? `${(new Date(dates.value[0])).getFullYear()}-${(new Date(dates.value[0])).getMonth()+1}-${(new Date(dates.value[0])).getDate()}` : '';
    let endDate = dates.value[1] ? `${(new Date(dates.value[1])).getFullYear()}-${(new Date(dates.value[1])).getMonth()+1}-${(new Date(dates.value[1])).getDate()}` : '';
    dateRange.value = dates.value[0] || dates.value[1] ? `${startDate}~${endDate}` : '';
    showDatePicker.value = (startDate != '' && endDate != '') ? false : true;
})

watch(()=> dateRange.value, () => {
    if(!dateRange.value){
        dates.value = [];
    }
})

</script>

<style lang="scss" scoped>
    :deep(.v-picker-title){
        display: none;
    }
    :deep(.v-picker__header){
        display: none;
    }

</style>