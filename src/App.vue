<template>
	<div class="container">
		<form class="card" @submit.prevent="handleSubmit">
			<h1>Анкета на Vue разработчика!</h1>
			<div class="form-control">
				<label for="name">Как тебя зовут?</label>
				<input type="text" id="name" placeholder="Введи имя" v-model="name" />
			</div>

			<div class="form-control">
				<label for="age">Выбери возраст</label>
				<input type="number" id="age" v-model.number="age" />
			</div>

			<div class="form-control">
				<label for="city">Твой город</label>
				<select id="city" v-model="city">
					<option value="spb">Санкт-Петербург</option>
					<option selected value="msk">Москва</option>
					<option value="kzn">Казань</option>
					<option value="nsk">Новосибирск</option>
				</select>
			</div>

			<div class="form-checkbox">
				<span class="label">Готов к переезду в Токио?</span>
				<div class="checkbox">
					<label
						><input type="radio" v-model="relocate" value="yes" name="trip" />
						Да</label
					>
				</div>

				<div class="checkbox">
					<label
						><input type="radio" v-model="relocate" value="no" name="trip" />
						Нет</label
					>
				</div>
			</div>

			<div class="form-checkbox">
				<span class="label">Что знаешь во Vue?</span>
				<div class="checkbox">
					<label
						><input
							type="checkbox"
							v-model="skills"
							name="skills"
							value="Vuex"
						/>
						Vuex</label
					>
				</div>
				<div class="checkbox">
					<label
						><input
							type="checkbox"
							v-model="skills"
							name="skills"
							value="Vue CLI"
						/>
						Vue CLI</label
					>
				</div>
				<div class="checkbox">
					<label
						><input
							type="checkbox"
							v-model="skills"
							name="skills"
							value="Vue Router"
						/>
						Vue Router</label
					>
				</div>
			</div>
			<div class="form-checkbox">
				<div class="checkbox">
					<label
						><input
							type="checkbox"
							name="agreement"
							v-model="agree"
							value="false"
						/>
						Вы согласны с правилами?</label
					>
				</div>
			</div>

			<button type="submit" :disabled="!agree" class="btn primary">
				Отправить
			</button>
		</form>
	</div>
</template>

<script>
	export default {
		data() {
			return {
				name: '',
				age: 23,
				city: 'msk',
				relocate: null,
				skills: [],
				agree: false,
			};
		},
		methods: {
			handleSubmit() {
				console.group('Form');
				console.log('Name:', this.name);
				console.log('Age:', this.age);
				console.log('City:', this.city);
				console.log('to Tokyo:', this.relocate);
				console.log('Skills:', this.skills);
				console.log('agree:', this.agree);
				console.groupEnd();
			},
		},
	};
</script>

<style></style>
