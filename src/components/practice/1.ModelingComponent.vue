<template>
    <!-- 단방향 바인딩 - 새로고침 하지 않아도 실시간으로 변경 -->
     <!-- 화면내에서는 this를 붙일 필요가 없다-->
    <h1>hello world {{language}}</h1>
    <!-- v-model 문법을 사용하면 양방향 데이터 바인딩 -->
    <input type="text" v-model="value">
    <button @click="changeValue()">변수변경</button>
    <button @click="showValue()">변수확인</button>

</template>

<script>
    export default{
        // data()함수는 화면에서 사용할 변수들을 정의.
        data(){
            return {
                language: "java",
                value: "java"
            }
        },

        // 개발자가 정의하는 함수는 methods안에 정의
        methods: {
            // 회원가입 당시 사용되는 vue의 메서드
            // submit(){
            //     const data = {email:this.email, password:this.password}
            //     axios.post("localhost:8080/member/create")
            // }

            changeValue(){
                // this의 의미는 현재 컴포넌트 객체 자신을 의미
                // this는 주로 컴포넌트 내부에 선언된 변수(data함수내)에 접근할 때 주로 사용
                this.value = "c++";
            },
            showValue(){
                alert(this.value)
            }
        }
    }
</script>
