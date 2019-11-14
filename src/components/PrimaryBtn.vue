<template>
    <div>
        <button 
            :disabled="disabled"
            :class="['btn', (disabled ? 'disabled':'primary-btn')]"
            v-on:click="addtoCount(1)"
        >{{title}}</button>
        <p>counter: {{counter}}</p>
    </div>
</template>
<script lang="ts">
import { Component, Prop, Vue, Emit } from "vue-property-decorator";

@Component
export default class PrimaryBtn extends Vue {
    @Prop() text!: string;
    @Prop() disabled!: boolean;
    @Prop() changeState!: Function;

    counter = 0;
    title= this.text;
    
    @Emit()
    addtoCount(n: number) {
        this.counter += n;
        this.changeState();
    }

}
// export default {
//     props: {
//         text: String
//     },
//     data(){
//         return {
//             title: 'Click me!',
//             counter: 1
//         }
//     },
//     methods: {
//         addtoCount(n: number) {
//             this.counter+=n;

//         }
//     }
// }

</script>
<style scoped lang="scss">
    .btn {
        border-radius: 5px;
         &:focus {
            outline: none;
        }
    }
    .primary-btn {
        background-color: white;
        color: #ddd;
        border: 1px solid #42b983;
        color: #42b983;
        box-shadow: 0 0 5px 0 #808080;
        &:hover {
            background-color: #42b983;
            color: white;
        }
    }
    .disabled {
        background-color: #808080;
        color: white;
    }
</style>