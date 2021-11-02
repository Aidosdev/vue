<template>
    <div class="user-card">
        <h1>Научу зарабатывать от 100 000тг. в час</h1>
        <div class="main-information">
            <img src="https://sun9-58.userapi.com/s/v1/ig2/q18vcIBmPNpmu7SVFma-jq8YDmVPkR-qKIh0Z-x82BrIzJP4ZCBcg6zOnsKWbNFUnDhdy_8KsKpUxiqdPPTITgnZ.jpg?size=200x200&quality=96&crop=4,233,1608,1609&ava=1" width="500px">
            <div class="info">
                <h2>
                    {{firstName.toUpperCase() + ' ' + lastName.toUpperCase()}}
                </h2>
                <strong class="coach">Бизнес коуч</strong>
                <ul>
                    <li>Учу людей делать РЕАЛЬНЫЕ бабки, на себя просто не хватило времени Х(</li>
                    <li>Не знаю, что такое "Успешный Успех", но знаю, что нужно ТЕБЕ!</li>
                    <li>Пообещал, что накачаюсь, когда кого-нибудь обману</li>
                </ul>
            </div>
        </div>
        <p>Участников: <strong>10</strong></p>
        <ul></ul>
    </div>
</template>

<script>
    export default {
        name: "UserCard",
        data() {
            return {
                firstName: 'Айдос',
                lastName: 'Кожанов',
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