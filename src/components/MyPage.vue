<template>
    <!-- 내 정보 조회 -->
     <!-- 문자열로 props를 넘길 경우 변수명="값", 그 외에는 :변수명 형태로 전달 -->
    <MemberDetailComponent
    :isMyPage="true" pageTitle="내회원정보"
    />

    <!-- 내 주문내역 조회 -->
     <OrderListComponent
     :isMyPage="true" pateTitle="내주문내역"
     />
</template>

<script>
import MemberDetailComponent from './MemberDetailComponent.vue';
import OrderListComponent from './OrderListComponent.vue';

    export default{
        data(){
            return{

            }
        },
        components:{
            MemberDetailComponent, OrderListComponent
        }
    } 
</script>