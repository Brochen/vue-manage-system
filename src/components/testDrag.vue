<template>
    <div id="app">
        <Dragable  :w="200" :h="200" :x="100" v-on:resizing="resize" v-on:dragging="resize" style="background: #666">
            <h3>Hello World!</h3>
            <p>{{ top }} х {{ left }} </p>
            <p>{{ width }} х {{ height }}</p>
        </Dragable>
        <Dragable  :w="200" :h="200" :x="100" v-on:resizing="resize" v-on:dragging="resize" style="background: grey">
            <h3>Hello World!</h3>
            <p>{{ top }} х {{ left }} </p>
            <p>{{ width }} х {{ height }}</p>
        </Dragable>
    </div>
</template>

<script>
    import Dragable from './Dragable';

    export default {
        name: 'app',

        components: {
            Dragable
        },

        data() {
            return {
                width: 0,
                height: 0,
                top: 0,
                left: 0
            }
        },

        methods: {
            resize(newRect) {
                this.width = newRect.width;
                this.height = newRect.height;
                this.top = newRect.top;
                this.left = newRect.left;
            }
        }
    }
</script>
