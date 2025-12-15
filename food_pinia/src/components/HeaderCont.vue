<template>
    <nav class="navbar navbar-inverse">
        <div class="container-fluid">
            <div class="navbar-header">
            <router-link class="navbar-brand" to="/">Pinia Router</router-link>
            </div>
            <ul class="nav navbar-nav">
            <li class="active"><router-link to="/">Home</router-link></li>
            <li class="dropdown">
                <a class="dropdown-toggle" data-toggle="dropdown" href="#">맛집
                <span class="caret"></span></a>
                <ul class="dropdown-menu">
                <li><router-link to="/food/find">맛집 검색</router-link></li>
                </ul>
            </li>
            <li><router-link to="/youtube/find">동영상 검색</router-link></li>
            
            </ul>
        </div>
    </nav>
</template>

<script setup>
/*
    vuex에 대한 라이브러리 : pinia
                                                            vuex        pinia
    state : 공유하는 데이터                                    O           O
    mutation : state에 값을 저장                               O           x
                동기적 처리
    actions : 사용자 요청에 따른 처리                           O           O
                                                                        this.state=값
    commit : action에서 처리 결과를 mutation으로 전송        commit('함수')
    namespace : 독립적인 모듈 생성                              O           X
                                                                           |
        1. 사용자 요청                                                    redux
                | dispatch
        2. actions에 있는 함수
                | commit
        3. actions에 mutation 함수
        4. state에 저장
        5. 처리된 결과 값 읽기 : dispatch를 이용해서 읽어온다

        => 기반 : 자바 스크립트 = 문법
                    .js , .jsx => ts , tsx
        => 스프링 : 자바문법
        -------------------------------------------- 라이브러리 함수를 익힌다
*/

</script>

<style scoped>

</style>