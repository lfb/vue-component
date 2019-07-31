<template>
    <button :class="'i-button i-button-size--' + size"
            :disabled="disabled"
            @click="handleEvent">
        <slot name="icon"></slot>
        <!-- 插槽默认-->
        <slot>按钮</slot>
    </button>
</template>

<script>
    function find(value, validList) {
        for (var i = 0, len = validList.length; i < len; i++) {
            if (value === validList[i]) {
                return true
            }
        }

        return false;
    }

    export default {
        name: "i-button",
        props: {
            disabled: {
                type: Boolean,
                default: false
            },
            size: {
                validator(value) {
                    return find(value, ['small', 'large', 'default'])
                },
                default: 'default'
            }
        },
        methods: {
            // 触发时间
            handleEvent(event) {
                this.$emit('on-click', event);
            }
        }
    }
</script>

<style scoped>
    .i-button {
        display: inline-block;
        padding: 0 10px;
        min-width: 80px;
        border-radius: 5px;
        border: none;
        outline: none;
        color: #fff;
        cursor: pointer;
        margin: 4px;
        background: #2d8cf0;
    }

    .i-button:disabled {
        opacity: 0.5;
        cursor: not-allowed;
    }


    .i-button-size--small {
        height: 28px;
        line-height: 28px;
        font-size: 12px;
    }

    .i-button-size--default {
        height: 32px;
        line-height: 32px;
        font-size: 14px;
    }

    .i-button-size--large {
        width: 100%;
        height: 36px;
        line-height: 36px;
        font-size: 14px;
    }

</style>
