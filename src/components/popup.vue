<template>
	<div class="text-center">
		<v-dialog max-width="600px">
			<template v-slot:activator="{ on }">
				<v-btn tile text v-on="on" class="success">
					Add new project
				</v-btn>
			</template>
			<v-card>
				<v-card-title>
					<h3>
						Add a New Project
					</h3>
				</v-card-title>
				<v-card-text>
					<v-form class="px-3">
						<v-text-field
							color="purple accent-4"
							label="Title"
							v-model="title"
							prepend-icon="mdi-folder"
						></v-text-field>
						<v-textarea
							color="purple accent-4"
							label="Information"
							v-model="content"
							prepend-icon="mdi-pencil"
						></v-textarea>

						<v-menu>
							<template v-slot:activator="{ on }">
								<v-text-field
									color="purple accent-4"
									label="Due date"
									prepend-icon="mdi-calendar-range"
									v-on="on"
									:value="formattedDate"
								>
								</v-text-field>
							</template>
							<v-date-picker v-model="due"></v-date-picker>
						</v-menu>

						<v-btn text tile class="success" @click="submit">
							Add Project</v-btn
						>
					</v-form>
				</v-card-text>
			</v-card>
		</v-dialog>
	</div>
</template>

<script>
import format from "date-fns/format";
import parseISO from "date-fns/parseISO";
export default {
	data() {
		return {
			title: "",
			content: "",
			due: null
		};
	},
	methods: {
		submit() {
			console.log(this.title, this.content);
		}
	},
	computed: {
		formattedDate() {
			return this.due ? format(parseISO(this.due), "do MMM yyyy") : "";
		}
	}
};
</script>

<style scoped></style>
