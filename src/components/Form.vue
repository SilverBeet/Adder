<template>
    <div>
        <div class="formWrapper">
            <form>
                <div class="inputWrapper">
                    <input required type="text" v-model="form.name" placeholder="Navn">
                    <input required type="text" v-model="form.hours" placeholder="Timer">
                    <input @click.prevent="sendData" type="submit" name="submit" class="submitBtn" value="Legg inn">
                </div>
            </form>
        </div>
        <tableApp :persons="persons"></tableApp>
    </div>
</template>

<script>
    import tableApp from './Table'
	export default {
		name: 'form-app',
        components: {
            tableApp
        },
		data: () => {
			return {
                persons:[],
				form: {
					name: null,
					hours: null
				}
			}
		},
        methods: {
			sendData() {
				this.persons.push({
					'name': this.form.name,
					'hours': this.form.hours,
				})
                this.form.name = this.form.hours = '';
			}
		}
	}
</script>

<style scope="css">
	.formWrapper {
		display: grid;
		height: 100%;
		width: 100%;
		padding: 50px;
		justify-content: center;
		width: 450px;
		height: auto;
		background: transparent;
		margin: 0 auto;
		margin-top: 125px;
		border: 1px solid rgba(165, 189, 30, 0.569);
	}

	.inputWrapper {
		display: grid;
		grid-gap: 10px;
	}

	input[type="text"] {
		font-family: monospace;
		display: block;
		background-color: transparent;
		border: none;
		border-bottom: 1px solid rgba(165, 189, 30, 0.569);
		margin: 0 auto;
		width: 250px;
		padding: 5px;
		padding-left: 0;
		font-size: 15px;
		outline:none;
		color: rgba(165, 189, 30, 0.569);
	}

	input::placeholder {
		opacity: .6;
		color: rgba(165, 189, 30, 0.569);
	}

	.submitBtn {
		display: block;
		font-family: monospace;
		font-size: 15px;
		margin: 0 auto;
		padding: 5px;
		width: 150px;
		border: 1px solid rgba(165, 189, 30, 0.569);
		margin-top: 40px;
		color: rgba(165, 189, 30, 0.569);
		outline: none;
		background-color: transparent;
	}
</style>