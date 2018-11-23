<template>
	<section>
		<header></header>
		<main>
			<div class="intro flex">
				<div class="flex flex-1">
					<div>
						<h1 class="title roboto">Control your heater.</h1>
						<p class="description roboto">Lorem ipsum dolor sit amet, consectetur adipisicing elit. lorem wd. turlupine !</p>
					</div>
				</div>
				<div class="flex flex-2">
					<div>
						<img src="@/assets/make-it-rain.svg" width="710"/>
					</div>
				</div>
			</div>
			<div class="divider">
				<div class="gradient"></div>
			</div>
			<div class="features roboto">
				<div class="text-align-center">
					<h2>What can it do?</h2>
				</div>
				<div class="features-list flex jc-space-between">
					<div class="feature">
						Ebola
					</div>
					<div class="feature">
						Childhood Cancer
					</div>
					<div class="feature">
						FightAIDS
					</div>
					<div class="feature">
						OpenZika
					</div>
					<div class="feature">
						Microbiome Immunity
					</div>
				</div>
			</div>
			<div class="flex roboto text-align-center">
				<p class="description description-health">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Facilis maiores suscipit, nostrum, sequi, doloribus blanditiis dolor vitae voluptas placeat porro itaque dolorum velit ex natus. Incidunt reiciendis deleniti reprehenderit in.</p>
			</div>

			<div class="flex roboto text-align-center">
				<div class="controller">
					<div class="flex text-align-center">
						<div class="content flex-center-middle">
							<div class="w-100">
								<p>Temperate actual</p>
								<p>28 °</p>
							</div>
						</div>
						<div class="content flex-center-middle">
							<div class="w-100">
								<p>Temperate target</p>
								<p>34 °</p>
							</div>
						</div>
					</div>
				</div>
			</div>
		</main>
	</section>
</template>

<script>

// - degres cellculs (fake)
// - degres que tu veux (fake) 
// - listes des recherches en cours ( entrain de miner) + (name + type + count)
// - liste des recherches termine (name + type + count)

// - jauge choisir connecter 

export default {
	name: 'HelloWorld',
	data () {
		return {
			msg: 'Welcome to Your Vue.js App'
		}
	}
}
</script>


<style scoped>

	.intro {
		margin: 5rem 0 3.5rem;
		-webkit-box-orient: horizontal;
		-webkit-box-direction: normal;
		-ms-flex-direction: row;
		flex-direction: row;
	}
	
	.title{
		font-weight: 700;
		font-size: 37px;
		margin: 0 0 1rem;
		color: #011F3F;
	}

	.description {
		font-weight: 300;
		font-size: 18px;
		line-height: 1.75rem;
		color: #777F88;
		padding-right: 15px;
	}
	
	.flex-1 {
		-webkit-box-align: center;
		-ms-flex-align: center;
		align-items: center;
		flex: 1;
	}

	.flex-2 {
		text-align: right;
		-webkit-box-flex: 2;
		-ms-flex: 2;
		flex: 2;
	}
	.flex-2 img {
		border-style: none;
    	max-width: 100%;
	}

	.divider {
		width: 100%;
		-webkit-transform: rotate(-2deg);
		transform: rotate(-2deg);
		position: absolute;
		z-index: -1;
		left: 0;
	}

	.gradient {
		width: 100%;
		height: 40px;
		background: #f6f6f6;
		background: linear-gradient(to bottom,#f6f6f6 0,#fff 100%);
	}

	.features {
		padding: 5rem 0 0;
		-webkit-box-pack: justify;
		-ms-flex-pack: justify;
		justify-content: space-between;
	}

	.features-list {
		flex-wrap: nowrap;
		margin: 3rem 0 1rem;
		-ms-flex-wrap: wrap;
		flex-wrap: wrap;
		justify-content: space-between;
	}

	.feature {
		font-weight: 400;
		display: block;
		width: 160px;
		height: 60px;
		line-height: 62px;
		text-align: center;
		border-radius: .5rem;
		margin: 0 0 1rem;
		color: #777F88;
		border: 1px solid rgba(119,127,136,.2);
		transition: all .15s ease-in-out;
		cursor: pointer;
	}

	.feature:hover {
	    border: 1px solid #777f88;
    	color: #2962FF;
   	}
	
	.description-health {
		width: 70%;
		margin: 0 auto;
	}

	.controller {
		background: #011F3F;
		padding: 1.5rem 1.5rem 0;
		border-top-left-radius: 1rem;
		border-top-right-radius: 1rem;
		width: 90%;
		max-width: 920px;
		margin: 0 auto;
		height: 600px;
		position: relative;
		bottom: -42px;
	}

	.controller .flex{
		width: 50%;
		-webkit-box-pack: justify;
		-ms-flex-pack: justify;
		justify-content: space-between;
	}

	.content {
		background-color: #fff;
		border-radius: 1rem;
		flex-wrap: nowrap;
		margin: 3rem 0 1rem;
		-ms-flex-wrap: wrap;
		flex-wrap: wrap;
		justify-content: space-between;
		font-weight: 400;
		width: 170px;
		height: 100px;
		line-height: 20px;
		text-align: center;
		border-radius: .5rem;
		margin: 0 0 1rem;
		color: #777F88;
		border: 1px solid rgba(119,127,136,.2);
		transition: all .15s ease-in-out;
		cursor: pointer;
	}

	.content p{
		margin-top: 5px;
	}

	.content:hover {
	    border: 1px solid #777f88;
    	color: #2962FF;
   	}
	
</style>
