<template>
    <div class="user-card">
        <h1>Научу зарабатывать от 100 000тг. в час</h1>
        <div class="main-information">
            <img src="https://pbs.twimg.com/profile_images/937142070992605184/GO70zooO_400x400.jpg" width="500px">
            <div class="info">
                <h2>
                    {{getAuthorFullName}}
                </h2>
                <strong class="coach">Бизнес коуч</strong>
                <ul>
                    <li>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Optio, eveniet!</li>
                    <li>Lorem ipsum dolor sit amet consectetur adipisicing elit.</li>
                    <li>Lorem ipsum dolor sit amet consectetur.</li>
                </ul>
            </div>
        </div>
        <p>Участников: <strong>{{users.length}}</strong></p>
        <ul>
            <li v-for="(user, index) in users" :key="index">
                 {{index + 1}} - {{getFullName(user)}} 
            </li>
        </ul>
        <button 
            type="button" 
            @click="prevPage()">Пред.
        </button>
        <button 
            v-for="page in pages" 
            :key="page"
            @click="currentPage = page">
            {{page}}
        </button>
        <button 
            type="button" 
            @click="nextPage()">След.
        </button>     
        <p>Страница {{currentPage}} из {{pages}}</p>
    </div>
</template>

<script>
    export default {
        name: "UserCard",
        data() {
            return {
                firstName: 'Steve',
                lastName: 'Rogers',
                users: [
                    {
                        firstName: 'Tony',
                        lastName: 'Stark',
                    },
                    {
                        firstName: 'Thor',
                        lastName: 'Odinson',
                    },
                    {
                        firstName: 'Bruce',
                        lastName: 'Banner',
                    },
                    {
                        firstName: 'Natasha',
                        lastName: 'Romanov',
                    },
                    {
                        firstName: 'Klint',
                        lastName: 'Barton',
                    }
                ],
                pages: 3,
                currentPage: 1
            }
        },
        computed: {
            getAuthorFullName() {
                return `${this.firstName} ${this.lastName}`.toUpperCase()
            }
        },
        methods: {
            getFullName(user) {
                return `${user.firstName} ${user.lastName}`
            },
            nextPage() {
                if (this.currentPage < this.pages) {
                    this.currentPage++
                }    
            },
            prevPage() {
                if (this.currentPage > 1) {
                    this.currentPage--
                }    
            },
            loadUsers(page) {
                console.log(`Загрузка пользователей: страница ${page}`)
            }
        },
        watch: {
            currentPage(page) {
                this.loadUsers(page)
            }
        }
    }
</script>

<style lang="scss">
    * {
        padding: 0;
        margin: 0;
        box-sizing: border-box;
    }

    img {
        width: 100%;
    }

    .user-card {
        padding: 20px;
        p {
            margin-top: 10px;
        }
        ul {
            list-style: none;
        }
    }

    .main-information {
        margin-top: 20px;
        width: 70%;
        display: flex;
        justify-content:  space-between;
        img {
            width: 40%;
        }
        .info {
            h2 {
                margin-bottom: 15px;
            }
            .coach {
                margin-bottom: 15px;
            }
            ul {
                margin-top: 1px;
                list-style: none;
                li {
                    padding: 5px 0;
                }
            }
        }
    }
</style>