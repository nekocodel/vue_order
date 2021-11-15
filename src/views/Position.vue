<template>
    <div>
        <mt-popup position="bottom" v-model="popupVisible" class="popup">
            <mt-picker :slots="slots" @change="onValuesChange"></mt-picker></mt-popup>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                popupVisible: true,
                      slots: [
                        {
                            values: ['1', '2', '3', '4', '5', '6'],
                            className: 'slot',
                        }
                        ]
            }
        },
        methods: {
            onValuesChange(picker, values) {
                    picker.setSlotValue(1,values[0]);
                    console.log(picker.getValues()[0]); 
            }
        },
    }
</script>

<style lang="scss">
.popup{
    width: 100%;
    .picker-slot{
        width: 100%;
    }
}
</style>