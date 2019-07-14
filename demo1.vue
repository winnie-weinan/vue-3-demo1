<template>
    <div>
        <ul>
            <li v-for="(item,index) in lists"
                @click="choose(index)"
                :class="{active:index == current && current!=''}"
                :key="index">
                    {{item}}
            </li>
        </ul>
        <button type="button" @click="add()">添加</button>
        <ul>
            <li v-for="(item,index) in target"
            :key="index"
            >
                {{item}}
            </li>
        </ul>
    </div>
   <!-- <button type="button" @click="add()">添加</button>-->
</template>

<script>
    export default {
        name: "demo1",
        data () {
            return{
                current:'',
                lists:[0,1,2,3,4,5,6,7],
                target:[]
            }
        },
        methods:{
            choose(index){
                console.log(index)
                this.current=index
            },
            add(){
                if (this.current===''){
                    return
                }
                this.target.push(this.lists[this.current])
                this.current=''
            }
        }
    }
</script>

<style scoped>
li.active{
    background: aquamarine;
}
ul,li{
    list-style: none;
}
</style>
