<template>
	<div class="projects">
		<h1 class="subheading grey--text">My Projects</h1>
		<v-container class="my-5">
			<v-expansion-panels>
				<v-expansion-panel v-for="project in myProjects" :key="project.title">
					<v-expansion-panel-header>{{
						project.title
					}}</v-expansion-panel-header>
					<v-expansion-panel-content>
						<v-card flat>
							<v-card-text class="grey--text">
								<div class="font-weight-bold mb-2">
									Due by {{ project.due }}
								</div>
								<div>{{ project.content }}</div>
							</v-card-text>
						</v-card>
					</v-expansion-panel-content>
				</v-expansion-panel>
			</v-expansion-panels>
		</v-container>
	</div>
</template>

<script>
export default {
	data() {
		return {
			projects: [
				{
					title: "Design a new Website",
					person: "Maciek Celiński ",
					due: "1st Jan 2011",
					status: "complete",
					content:
						"Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!"
				},
				{
					title: "Code up the homepage",
					person: "Net Ninja",
					due: "13th Sep 2014",
					status: "ongoing",
					content:
						"Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!"
				},
				{
					title: "Design video thumbnails",
					person: "Brad Traversy",
					due: "2nd March 2017",
					status: "overdue",
					content:
						"Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!"
				},
				{
					title: "Create a community forum",
					person: "Net Ninja",
					due: "21th Jul 2019",
					status: "decline",
					content:
						"Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!"
				}
			]
		};
	},
	// gdyby tu było methods to by nie zadziałało !!!!!!
	computed: {
		myProjects() {
			return this.projects.filter(project => {
				return project.person === "Net Ninja";
			});
		}
	}
};
</script>
