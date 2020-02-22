# vue-intermediate
## REFACTORING

**문제점**
1. add 할 때 localStorage에는 저장이 되지만, 새로고침하지 않으면 화면이 갱신되지 않음     
2. clear all로 화면을 지우면 localStorage는 모두 지워지지만 화면에 자동으로 반영되지 않음       
-> 각각의 component 간 통신이 되지 않기 때문 ->todoItems가 TodoList.vue에 있기 때문      

   
    
**해결**       
데이터는 모두 App.vue에 두고 각각의 컴포넌트에서는 동작만 넘기고 받도록 재설계함
