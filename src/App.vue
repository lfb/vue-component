<template>
    <div id="app">
        <i-button size="small">按钮 1</i-button>
        <i-button>按钮 2</i-button>
        <i-button>按钮 3</i-button>
        <i-button>
            <span slot="icon">🍓</span>
            海欣甜派
        </i-button>
        <i-button disabled>禁用</i-button>
        <i-button size="large"
                  @on-click="handleEvent"
                  @click.native="handleNativeEvent">
            <span slot="icon">🍓</span>
            点我触发
        </i-button>
    </div>
</template>

<script>
    import IButton from './components/i-button'

    export default {
        name: 'app',
        components: {
            IButton
        },
        methods: {
            // 组件的事件
            handleEvent(event) {
                console.log(event);
            },
            // 原生的事件
            handleNativeEvent() {
                console.log('this a native event!');
            }
        }
    }
</script>

<style>

</style>
