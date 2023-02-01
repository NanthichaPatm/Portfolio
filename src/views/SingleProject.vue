<script>
import feather from 'feather-icons';
import ProjectHeader from '../components/projects/ProjectHeader.vue';
import ProjectGallery from '../components/projects/ProjectGallery.vue';
import ProjectInfo from '../components/projects/ProjectInfo.vue';
import projects from '../data/projects';
// import ProjectRelatedProjects from '../components/projects/ProjectRelatedProjects.vue';

export default {
	name: 'Projects',
	components: {
		ProjectHeader,
		ProjectGallery,
		ProjectInfo,
		// ProjectRelatedProjects,
	},
	data: () => {
		return {
			projectID:'',
			project:{},
			singleProjectHeader: {
				singleProjectTitle: 'Project Management UI',//projects.title//
				singleProjectDate: 'Jul 26, 2021', //projects.singleProjectDate//
				singleProjectTag: 'Frontend',
			},
			projectImages: [
				{
					id: 1,
					title: 'Kabul Project Management UI', //projects.title//
					img: require('@/assets/images/ui-project-1.jpg'), //projects.img//
				},
				{
					id: 2,
					title: 'Kabul Project Management UI',
					img: require('@/assets/images/web-project-2.jpg'),
				},
				{
					id: 3,
					title: 'Kabul Project Management UI',
					img: require('@/assets/images/mobile-project-2.jpg'),
				},
			],
			projectInfo: {
				objectivesHeading: 'Objective',
				objectivesDetails:
					'Lorem ipsum dolor sit amet consectetur adipisicing elit. Optio, natus! Quibusdam enim quod in esse, mollitia molestias incidunt quas ipsa accusamus veniam.',
				technologies:
					{
						title: 'Tools & Technologies',
						techs: [''],
						git:''
					},
				projectDetailsHeading: 'Description:',
				projectDetail:'Losfljvnslojvnsbfsbsdfdfsfnvlsdv', //projects.projectDetail//
			},
		};
	},
	mounted() {
		this.projectID = this.$route.params.id;
		console.log(typeof(this.projectID))
		feather.replace();
		console.log(this.projectID)
		this.project = projects.find((p) => p.id == this.projectID);
		console.log(this.project);

		this.singleProjectHeader.singleProjectTitle = this.project.title;//projects.title//
		this.singleProjectHeader.singleProjectDate = this.project.singleProjectDate; //projects.singleProjectDate//
		this.projectImages[0].title = this.project.title; //projects.title//
		this.projectImages[0].img = this.project.img; //projects.img//
		this.projectImages[1].title = this.project.title; //projects.title//
		this.projectImages[1].img = this.project.img2; //projects.img//
		this.projectImages[2].title = this.project.title; //projects.title//
		this.projectImages[2].img = this.project.img3; //projects.img//
		this.projectInfo.objectivesDetails = this.project.objectivesDetails;
		this.projectInfo.technologies.techs = this.project.techs;
		this.projectInfo.technologies.git = this.project.git;
		this.projectInfo.projectDetail = this.project.projectDetail; //projects.projectDetail//
	},
	updated() {
		feather.replace();
	},
	methods: {},
};
</script>

<template>
  <div class="container mx-auto mt-10 sm:mt-20">
    <!-- Project header -->
    <ProjectHeader :singleProjectHeader="singleProjectHeader" />

    <!-- Project gallery -->
    <ProjectGallery :projectImages="projectImages" />

    <!-- Project information -->
    <ProjectInfo :projectInfo="projectInfo" />
  </div>
</template>

<style scoped></style>
