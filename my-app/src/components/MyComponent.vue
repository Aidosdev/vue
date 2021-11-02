<template>
    <div class="root">
        <label for="">
            Введите email:
            <input 
                type="email" 
                v-bind:value="email"
                v-on:input="emailInput($event.target.value)" 
            />      
        </label>    
        <label for="">
            Введите пароль:
            <input 
                type="password" 
                v-bind:value="password" 
                v-on:input="passwordInput($event.target.value)" 
            />    
        </label>   
        <div>
            <button v-on:click="removeGoodCount">-</button>
            <input 
                type="number"
                min="1"
                max="10"   
                v-model="goodCount"
                v-on:input="selectCountGoods($event.target.value)"
            />
            <button v-on:click="addGoodCount">+</button> 
        </div>
    </div>
</template>

<script> 
    export default {
        name: 'MyComponent',
        data() {
            return { 
                email: 'example@mail.ru',
                password: '12345678',
                goodCount: 1
            }
        },
        methods: {
            emailInput(e) {
                this.email = e
            },
            passwordInput(e) {
                this.password = e
            },
            selectCountGoods(e) { 
                this.goodCount = e
            },
            addGoodCount() {
                if (this.goodCount < 10) {
                    this.goodCount++ 
                }
            },
            removeGoodCount() {
                if (this.goodCount > 1) {
                    this.goodCount-- 
                }
            }
        }
    } 
</script>
