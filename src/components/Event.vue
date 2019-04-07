<template>
		<div>
				name: {{name || '--'}}
				<br>
				<input  :value="name" @change="handleChange">
				<br>
				<br>
				<div @click="handleDivClick">
						<button @click="handleClick">重置成功</button>
						<button @click.stop="handleClick">重置失败</button>

				</div>
		</div>
</template>

<script>
    export default {
        name: "Event.vue",
        props: {
            name: String
            // value: String
        },
        methods: {
            handleChange(e){
                // alert('change')
                this.$emit('change', e.target.value )
            },
            handleDivClick(){
                this.$emit('change','')
                // alert('div')
            },
            handleClick(){
                // alert(e)
                // alert('button')
            }
        }
    }
</script>

<style scoped>

</style>