<template>
		<!--<li>{{msg}} {{todo.id}}</li>-->
		<li class="item">
				<!--{{list}}-->
				<input type="checkbox" v-model="isCheck">
				<slot name="item" :isCheck="isCheck" v-bind="{aaa}"></slot>
		</li>
</template>

<script>
    export default {
        name: "todoItem123",
        props: ['list'],
        data() {
            return{
                isCheck: false,
                aaa: 'haha'
            }
        }
        // props: {
        //     msg: String,
        // 		todo: Object
        // }
    }
</script>

<style scoped>
		.item{
				color: orange;
		}
</style>