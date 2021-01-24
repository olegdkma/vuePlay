<template>
    <div class="vs-preview-wrap">
        <p>{{ options }}</p>
        <form class="vs-preview-form" :class="[formSizeClass]">
            <div v-for="(item,index) in 5"
                 :key="item"
            >
                <label :class="[colorClass, fontClass]">Label</label>
                <input :class="[colorClass, fontClass, elementSizeClass]">
            </div>

        </form>

    </div>
</template>

<script>
export default {
    name: "resulting-form",
    props: {
        options: {
            type: Object,
            default : {
                formColor: 'standart',
                fontSize: 'standart',
                formSize: 'standart'
            }
        }
    },
    data () {
        return{
            classes: ['standart', 'small', 'medium', 'large']
        }
    },
    computed: {
        colorClass: function () {
            return `vs-style_color_${this.options.formColor}`
        },
        fontClass: function () {
            return `vs-style_font_${this.classes[this.options.fontSize]}`
        },
        formSizeClass: function () {
            return `vs-style_form-size_${this.classes[this.options.formSize]}`
        },
        elementSizeClass: function () {
            return `vs-style_el-size_${this.classes[this.options.formSize]}`
        }
    }
}
</script>

<style lang="scss">
    .vs-preview-wrap{
        padding: 50px 0;
        border-top: 1px solid #000;
        height: 100%;
    }
    .vs-preview-form{
        padding: 30px;
        width: 80%;
        margin: auto;
        height: 100%;
        border: 1px solid #000;
        input{
            width: 100% ;
        }
    }
    .vs-style_form-size{
        &_standart{
            font-size: 14px;
        }
        &_small{
            font-size: 12px;
        }
        &_medium{
            font-size: 13px;
        }
        &_large{
            font-size: 16px;
        }
    }

    .vs-style_el-size{
        &_standart{
            height: 24px;
        }
        &_small{
            height: 12px;
        }
        &_medium{
            height: 28px;
        }
        &_large{
            height: 32px;
        }
    }
    .vs-style_color{
        &_standart{
            color: #000;
        }
        &_red{
            color: red;
        }
        &_blue{
            color: blue;
        }
        &_green{
            color: green;
        }
    }
    .vs-style_font{
        &_standart{
            font-size: 14px;
        }
        &_small{
            font-size: 12px;
        }
        &_medium{
            font-size: 13px;
        }
        &_large{
            font-size: 16px;
        }
    }
    .vs-style_size{
        &_standart{

        }
        &_smal{
            font-size: 12px;
        }
        &_medium{
            font-size: 13px;
        }
    }


</style>