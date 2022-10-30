<template>
    <div class="login-button">
    <GoogleLogin :params="params" :onSuccess="onSuccess" :onFailure="onFailure">Google Login</GoogleLogin>

    </div>
</template>
<script>
import GoogleLogin from 'vue-google-login';

    export default {
            name: 'LoginPage',
            components: {
                GoogleLogin
            },
            data() {
                return {
                    // client_id is the only required property but you can add several more params, full list down bellow on the Auth api section
                    params: {
                        client_id: "489376918742-2h48reb78ltrcpib903lbv3j10jevs08.apps.googleusercontent.com"
                    },
                    // only needed if you want to render the button with the google ui
                    renderParams: {
                        width: 250,
                        height: 50,
                        longtitle: true
                    }
                }
            },
            methods: {
                onSuccess(googleUser) {
                    console.log(googleUser.getBasicProfile(), googleUser);
                },
                onFailure(error) {
                    console.log('failed with login', error);
                },
            }
        }

</script>

<style scoped>
.login-button {
    border: 1px solid gray;
    width: 10em;
    height: 3em;
    border-radius: 4px;
    margin: auto;
}
</style>