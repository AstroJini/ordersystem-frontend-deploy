<template>
        <div>라우트화면 3</div>
</template>

<script>
import axios from 'axios';

    export default{
        data(){
            return{
                id : null
            }
        },
        created(){
            // 라우터에서 전달된 id값(param)꺼내기
            this.id = this.$route.params.postId;
            // 서버 id값으로 데이터 요청
            const response = axios.get("http://localhost:8080/post/detail/"+this.id);
            console.log(response);
        },
        methods:{

        }
    }
</script>