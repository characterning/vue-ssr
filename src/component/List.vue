<template>
    <div class="wrap">
        <ul>
            <li v-for="(item,index) in list.contents" @click="showTitle(item.content.title)">
                <img :src="item.content.image">
                <p>
                    {{item.content.title}}
                </p>
            </li>
        </ul>
    </div>
</template>

<script>
    import Vue from 'vue'
    import {
        mapGetters
    } from 'vuex'
    import {
        LIST
    } from '../store/mutation-types'
    const computed = {
        ...mapGetters([
            'list'
        ])
    }
    export default {
        data() {
            return {}
        },
        methods:{
            showTitle(title) {
                alert(title)
            }
        },

        computed
    }
</script>
<style lang="less">
    ul {
        width: 100%;
        list-style: none;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        margin: 0 auto;
        justify-content: center;
    }

    li {
        
        height: 270px;
        margin-right: 30px;
        background-color: #f2f2f2;
        cursor: pointer;
        margin-top: 10px;
        -flex-grow:1
    }

    img {
        width: 380px;
        height: 214px;
    }

    p {
        width: 380px;
        padding-left: 15px;
        font-size: 16px;
    }
</style>