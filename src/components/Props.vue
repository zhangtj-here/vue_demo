<template>
		<div>
				name: {{name}},
				<br>
				type: {{type}},
				<br>
				list: {{list}}
				<br>
				isVisible: {{isVisible}}
				<br>
				<button @click="handleClick">change type</button>
		</div>
</template>

<script>
    export default {
        name: "props",
        // inheritAttrs: false,
        props: {
            name: String,
            type: {
                validator: function (value) {
                    return ["success","warning","danger"].includes(value)
                }
            },
            list: {
                type: Array,
                default: () => []
            },
            isVisible: {
                type: Boolean,
                default: false
            },
            onChange: {
                type: Function,
                default: () => {}
            }
        },
        methods: {
            handleClick() {
                // this.type = "warning"
                this.onChange(this.type === 'success'?'warning':'success')
            }
        }


    }
</script>

<style scoped>

</style>