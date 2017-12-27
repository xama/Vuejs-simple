<template>
    <div class="test">
        <input type="text" v-model="title">
        <h1>{{title}}</h1>
        <p>{{user.firstName}}</p>
        <span v-if="showname">
            <p v-text="user.lastName"></p>
        </span>
        <span v-else="showname">Nobody</span>
        <ul>
            <li v-for="item in items">{{item.title}}</li>
        </ul>
        <button v-on:click="greet('Hello world')">Say greeting</button>
        <br/>
        <input type="text" v-on:keyup="pressKey" v-on:keyup.enter="enterHit">
        <hr>
        <input type="text" v-model="user.firstName">
        <input type="text" v-model="user.lastName">
        <h3>{{fullName}}</h3>
        <h3>{{msg}}</h3>
    </div>
</template>

<script>
    export default {
        name: 'test',
        props: {
            msg: {
                type: String,
                default: "Foo bar"
            }
        },
        data() {
            return {
                title: 'Hello World',
                user: {
                    firstName: 'Joh',
                    lastName: 'Lahn'
                },
                showname: false,
                items: [
                    {title: 'Item One'},
                    {title: 'Item Two'},
                    {title: 'Item Three'},
                ]
            }
        },
        methods: {
            greet: function(greeting) {
                alert(greeting);
            },
            pressKey: function() {
                console.log('pressed');
            },
            enterHit: function() {
                console.log('you hit enter');
            },
        },
        computed: {
            fullName: function() {
                return this.user.firstName + ' ' + this.user.lastName;
            }
        }
    }
</script>

<style scoped>

</style>