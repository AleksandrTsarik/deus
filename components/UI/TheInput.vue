<template>
	<div v-if="type === 'text'" class="block-input">
		<label>
			<span v-if="name" class="block-input__name">{{ name }}</span>
			<input type="text" :value="value" :placeholder="placeholder">
		</label>
	</div>
	<div v-else-if="type === 'tel'" class="block-input">
		<label>
			<span v-if="name" class="block-input__name">{{ name }}</span>
			<MaskInput type="tel"  v-model="phoneNumber" mask="+7(###) ###-##-##" placeholder="+7 (-&#45;&#45;) -&#45;&#45; &#45;&#45; &#45;&#45;" />
		</label>
	</div>
	<div v-else-if="type === 'email'" class="block-input">
		<label>
			<span v-if="name" class="block-input__name">{{ name }}</span>
			<input :value="value" type="email" :placeholder="placeholder">
		</label>
	</div>
</template>

<script>
import { MaskInput } from 'vue-3-mask';
export default {
	components: {
		MaskInput
	},
	props: {
		value: {
			type: [String, Number],
			default: ''
		},
		label: {
			type: String,
			default: ''
		},
		name: {
			type: String,
			default: ''
		},
		type: {
			type: String,
			defrault: '',
			require: true
		},
		placeholder: {
			type: String,
			default: '',
			require: true
		}
	},
	data() {
		return {
		}
	}
}
</script>

<style lang="scss">
.block-input {
	margin-bottom: 30px;
	&:last-child {
		margin-bottom: 0;
	}
	input {
		width: 100%;
		text-overflow: ellipsis;
		border-bottom: solid 1px var(--grey3);
		font-size: 18px;
		font-weight: 400;
		padding: 10px 0;
	}
	&__name {
		color: #000;
		font-size: 20px;
		font-weight: 500;
	}
}

</style>