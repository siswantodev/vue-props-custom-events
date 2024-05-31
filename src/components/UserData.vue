<template>
	<div>
		<form @submit.prevent="submitUserData">
			<div>
				<label>Name :</label>
				<input type="text" v-model="enteredName" />
			</div>
			<div>
				<label>Age :</label>
				<input type="number" v-model="enteredAge" />
			</div>
			<button>Add User</button>
		</form>
	</div>
</template>

<script>
export default {
	emits: ['add-user'],
	data() {
		return {
			enteredName: '',
			enteredAge: '',
		};
	},
	methods: {
		submitUserData() {
			this.$emit('add-user', this.enteredName, this.enteredAge);
		},
	},
};
</script>
