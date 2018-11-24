<template>
	<section>
		<header>
			
		</header>
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
						<div class="w-100">
							<div class="flex text-align-center">
								<div class="temp-actual relative content flex-center-middle">
									<div class="w-100">
										<p>Temperature actual</p>
										<span>{{tempActual}} °</span>
									</div>
								</div>
								<div class="temp-target content relative flex-center-middle">
									<div class="w-100">
										<p>Temperature target</p>
										<span>{{tempTarget}} °</span>
									</div>
								</div>
								<div class="process relative content flex-center-middle">
									<div class="w-100">
										<p>Processor used</p>
										<span>{{proccesor}} %</span>
									</div>
								</div>
							</div>
						</div>
						
						<div class="w-100 blanche-bg">
							<input type="range" id="start" name="volume" min="15" max="30"  v-model="tempTarget" @change="changeTemp()">
						</div>


						<div class="w-100 blanche-bg roboto"><p>list n 1</p></div>
						<table class="roboto">
							<thead>
								<tr>
									<th scope="col"></th>
									<th scope="col">Komit</th>
									<th scope="col">Article</th>
									<th scope="col">Wiki</th>
								</tr>
							</thead>
							<tbody>
								<tr>
									<th scope="row">Like</th>
									<td>test</td>
									<td>test</td>
									<td>test</td>
								</tr>
								<tr>
									<th scope="row">Like</th>
									<td>test</td>
									<td>test</td>
									<td>test</td>
								</tr>
								<tr>
									<th scope="row">Like</th>
									<td>test</td>
									<td>test</td>
									<td>test</td>
								</tr>
							</tbody>
						</table>
						
						<div class="w-100 blanche-bg roboto"><p>list n 2</p></div>
						<table class="roboto">
							<thead>
								<tr>
									<th scope="col"></th>
									<th scope="col">Komit</th>
									<th scope="col">Article</th>
									<th scope="col">Wiki</th>
								</tr>
							</thead>
							<tbody>
								<tr>
									<th scope="row">Like</th>
									<td>test</td>
									<td>test</td>
									<td>test</td>
								</tr>
								<tr>
									<th scope="row">Like</th>
									<td>test</td>
									<td>test</td>
									<td>test</td>
								</tr>
								<tr>
									<th scope="row">Like</th>
									<td>test</td>
									<td>test</td>
									<td>test</td>
								</tr>
							</tbody>
						</table>
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
	data () {
		return {
			proccesor: 0,
			tempActual: 0,
			tempTarget: 20
		}
	},
	mounted() {
		let vm = this;
		setInterval(function(){
			vm.$http.get('/').then((response) => {
				vm.tempActual = response.data.temp;
			})
		}, 1000);
	},
	methods: {
		changeTemp() {
			this.$http.post('/temp/'+ this.tempTarget + '').then((response) => {
			  console.log(response.data)
			})
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
		padding: 2.5rem 2.5rem 0;
		border-top-left-radius: 1rem;
		border-top-right-radius: 1rem;
		width: 90%;
		max-width: 920px;
		margin: 0 auto;
		position: relative;
		bottom: -42px;
	}

	.controller .flex{
		background-color: #fff;
		height: 100%;
		border-top-left-radius: 1rem;
		border-top-right-radius: 1rem;
		-webkit-box-pack: justify;
		-ms-flex-pack: justify;
		justify-content: space-between;
	}

	.content {
		background-color: #f8f8f8;
		border-radius: 1rem;
		flex-wrap: nowrap;
		margin: 1.5rem;
		-ms-flex-wrap: wrap;
		flex-wrap: wrap;
		justify-content: space-between;
		font-weight: 400;
		width: 170px;
		height: 100px;
		line-height: 20px;
		text-align: center;
		border-radius: .5rem;
		color: #302d2d;
		border: 1px solid rgba(119,127,136,.2);
		transition: all .15s ease-in-out;
		cursor: pointer;
	}
	
	.content p{
		margin-bottom: 12px;
		font-size: 17px;
		position: absolute;
		top: 10px;
		left: 10px;
	}

	.content span{
		font-weight: 700;
		font-size: 40px;
		position: absolute;
		bottom: 25px;
		right: 15px;
	}

	.content:hover {
	    border: 1px solid #777f88;
    	color: #575353;
   	}
		
	.temp-actual {
		background-color: #9fdb83;
	}

	.temp-target {
		background-color: #cbd4ed;
	}
	
	.process {
		background-color: #efe2cb;
	}

	table {
		width: 100%;
		max-width: 100%;
		background-color: transparent;
		border-collapse: collapse;
		display: table;
		border-spacing: 2px;
		border-color: grey;
		border: 1px solid #e4e5e6;
	}

	thead {
		display: table-header-group;
    	vertical-align: middle;
    	border-color: inherit;
	}

	thead th {
    	color: #e4e5e6;
    	background-color: #23282c;
    	border-color: #343b41;
	}
	
	tbody {
		display: table-row-group;
		vertical-align: middle;
		border-color: inherit;
	}
	tr{
		display: table-row;
		vertical-align: inherit;
		border-color: inherit;
		border-top: 1px solid #777F88;
		background-color: #fdfdfd;
	}

	tr:hover{
		background-color: #f5f1f1;
	}
	
	tbody td, tbody th {
		padding: .75rem;
		vertical-align: top;
		border-top: 1px solid #c8ced3;
	}


	input[type=range] {
		height: 32px;
		-webkit-appearance: none;
		margin: 10px 0;
		width: 70%;
	}
	input[type=range]:focus {
		outline: none;
	}
	input[type=range]::-webkit-slider-runnable-track {
		width: 100%;
		height: 9px;
		cursor: pointer;
		animate: 0.2s;
		box-shadow: 0px 0px 0px #000000;
		background: #E3E3E3;
		border-radius: 37px;
		border: 0px solid #000000;
	}
	input[type=range]::-webkit-slider-thumb {
		box-shadow: 0px 0px 0px #000000;
		border: 1px solid #E3E3E3;
		height: 25px;
		width: 25px;
		border-radius: 47px;
		background: #3D3D3D;
		cursor: pointer;
		-webkit-appearance: none;
		margin-top: -8.5px;
	}
	input[type=range]:focus::-webkit-slider-runnable-track {
		background: #E3E3E3;
	}
	input[type=range]::-moz-range-track {
		width: 100%;
		height: 9px;
		cursor: pointer;
		animate: 0.2s;
		box-shadow: 0px 0px 0px #000000;
		background: #E3E3E3;
		border-radius: 37px;
		border: 0px solid #000000;
	}
	input[type=range]::-moz-range-thumb {
		box-shadow: 0px 0px 0px #000000;
		border: 1px solid #E3E3E3;
		height: 25px;
		width: 25px;
		border-radius: 47px;
		background: #3D3D3D;
		cursor: pointer;
	}
	input[type=range]::-ms-track {
		width: 100%;
		height: 9px;
		cursor: pointer;
		animate: 0.2s;
		background: transparent;
		border-color: transparent;
		color: transparent;
	}
	input[type=range]::-ms-fill-lower {
		background: #E3E3E3;
		border: 0px solid #000000;
		border-radius: 74px;
		box-shadow: 0px 0px 0px #000000;
	}
	input[type=range]::-ms-fill-upper {
		background: #E3E3E3;
		border: 0px solid #000000;
		border-radius: 74px;
		box-shadow: 0px 0px 0px #000000;
	}
	input[type=range]::-ms-thumb {
		margin-top: 1px;
		box-shadow: 0px 0px 0px #000000;
		border: 1px solid #E3E3E3;
		height: 25px;
		width: 25px;
		border-radius: 47px;
		background: #3D3D3D;
		cursor: pointer;
	}
	input[type=range]:focus::-ms-fill-lower {
		background: #E3E3E3;
	}
	input[type=range]:focus::-ms-fill-upper {
		background: #E3E3E3;
	}
</style>
