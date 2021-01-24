<template>
    <div>
        <form

                ref="form"
                @submit.prevent="formStyleSettings"
                class="vs-settings-form"
        >
            <label >font Size  (standart/small/medium/large)</label>
            <input type="number" max="3" min="0" v-model="styleSettings.fontSize">
            <label >input height (standart/small/medium/large)</label>
            <input type="number" max="3" min="0" v-model="styleSettings.formSize">

            <label >text color</label>
            <select v-model="styleSettings.formColor">

                <option
                    v-for="(item,index) in colors"
                    :key="item"
                    :value="item">

                    {{ item }}
                </option>
            </select>
            <button
           type="submit"
            >Submit</button>

        </form>
    </div>

</template>

<script>
export default {
name: "aside-form",
    data () {
    return {
        styleSettings: {
            formColor: 'red',
            fontSize: 0,
            formSize: 0,
        },
        colors: ['red', 'green', 'blue'],
    }
    },
    methods : {
        formStyleSettings () {
            this.$emit('formStyleSettings', this.styleSettings)
        }
    }
}
</script>

<style lang="scss">
    .vs-settings-form{
        display: flex;
        flex-direction: column;
        border: 1px solid salmon;
        width: 100% ;
        height: 100vh;
        padding: 30px;
        //width: 500px;
    }
</style>