<template>
    <v-container>
        <v-row justify="center">
            <v-col cols="6">
                <v-card>
                    <v-card-title class="text-h5 text-center">
                        로그인
                    </v-card-title>
                    <v-card-text>
                        <v-form>
                            <v-text-field
                                label="email"
                                v-model="email"
                                type="email"
                                prepend-icon="mdi-email"
                            />
                            <v-text-field
                                label="password"
                                v-model="password"
                                type="password"
                                prepend-icon="mdi-lock"
                            />
                            <v-row>
                                <v-col>
                                    <!-- block : 속한 row에서 너비를 꽉 채우는 옵션 -->
                                    <v-btn color="primary" block @click="memberLogin()">
                                        등록
                                    </v-btn>
                                </v-col>
                            </v-row>
                        </v-form>
                    </v-card-text>
                </v-card>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
import axios from 'axios';

    export default{
        data(){
            return{
                email: "",
                password: "",
            }
        },
        methods: {
            async memberLogin(){
                try{
                    const data = {email:this.email, password:this.password};
                    const response = await axios.post(`${process.env.VUE_APP_API_BASE_URL}/member/doLogin`, data);
                    const accessToken = response.data.result.accessToken;
                    const refreshToken = response.data.result.refreshToken;
                    localStorage.setItem("accessToken", accessToken);
                    localStorage.setItem("refreshToken", refreshToken);
                    window.location.href = "/";
                } catch(e){
                    console.log(e);
                    alert(e.response.data.status_message);
                }
            }
        }
    }
</script>