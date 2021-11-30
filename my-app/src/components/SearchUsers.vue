<template>
    <div class="search">
        <h2>Я найду тебя!</h2>
        <input type="text" v-model="message">
        <p>Всего имен: {{users.length}}, совпадений: {{getSearch.length}}</p>
        <ul>
            <li v-for="(user, index) in getSearch" :key="index">
                {{user.name}}
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: "SearchUsers",
        data() {
            return {
                users: [
                    {
                        name: 'Aidos', 
                    },
                    {
                        name: 'Aidar' 
                    },
                    {
                        name: 'Sultan' 
                    },
                    {
                        name: 'Dosjan' 
                    }
                ], 
                message: ''
            }
        },
        computed: {
            getSearch() { 
                if (this.message == '') {
                    return this.users
                } else {
                    return this.users.filter(item => {
                         return item.name.toLowerCase().includes(this.message.toLowerCase())
                    }) 
                }
            }
        } 
    }
</script>

<style lang="scss">
    .search {
        display: flex;
        flex-direction: column;
        width: 100%;
        h2 {
            color: cadetblue;
        }
        input {
            width: 20%;
            border: 1px solid cadetblue;
            outline: none;
            padding: 5px;
        }
        ul {
            list-style: none;
        }
    }
</style>