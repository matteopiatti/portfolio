<script>
	import Rocket from '../lib/Rocket.svelte'
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<section class="star-background scroll-smooth snap-y snap-mandatory h-[100vh] overflow-y-scroll relative this-is-the-scroll-element">

<Rocket />

	<secion class="snap-center w-screen h-[100vh] flex items-center justify-center">
		<article class="max-w-3xl p-4 flex justify-evenly">
			<h1 class="font-pixel text-white text-7xl">Welcome to my Universe</h1>
		</article>
	</secion>

	<secion class="snap-center w-screen h-[100vh] flex items-center justify-center">
		<article class="max-w-3xl p-4 flex justify-evenly">
			<figure class="group max-w-xs hover:border-2 p-4 rounded-full relative transition-all">
				<h3 class="transition-all opacity-0 group-hover:opacity-100 absolute uppercase text-white underline underline-offset-4 -left-[115px] -top-[34px]">Æelerth-58</h3>
				<span class="transition-all opacity-0 group-hover:opacity-100 absolute w-20 border-b-2 rotate-45 -left-[21px]"></span>
				<img class="w-full" src="/images/planets/planet_blue_orange.gif" alt="shut up">
			</figure>
	
			<figure class="group w-[10%] h-[10%] self-center hover:border-2 rounded-full relative transition-all">
				<h3 class="transition-all opacity-0 group-hover:opacity-100 absolute uppercase text-white underline underline-offset-4 left-[94px] -top-[60px]">Some asteroid</h3>
				<span class="transition-all opacity-0 group-hover:opacity-100 absolute w-10 border-b-2 -rotate-45 left-[60px]"></span>
				<img class="w-full" src="/images/asteroids/1608527793.png" alt="shut up">
			</figure>
		</article>
	</secion>

	<secion class="snap-center w-screen h-[100vh] flex items-center justify-center">
		<article class="max-w-3xl p-4 flex justify-evenly">
			<figure class="group max-w-xs hover:border-2 p-4 rounded-full relative transition-all">
				<h3 class="transition-all opacity-0 group-hover:opacity-100 absolute uppercase text-white underline underline-offset-4 -left-[71px] -top-[34px]">Gridat</h3>
				<span class="transition-all opacity-0 group-hover:opacity-100 absolute w-20 border-b-2 rotate-45 -left-[21px]"></span>
				<img class="w-full" src="/images/planets/gas_giant_ring.gif" alt="shut up">
			</figure>
	
			<figure class="group w-[10%] h-[10%] self-center hover:border-2 rounded-full relative transition-all">
				<h3 class="transition-all opacity-0 group-hover:opacity-100 absolute uppercase text-white underline underline-offset-4 left-[94px] -top-[60px]">Some asteroid</h3>
				<span class="transition-all opacity-0 group-hover:opacity-100 absolute w-10 border-b-2 -rotate-45 left-[60px]"></span>
				<img class="w-full" src="/images/asteroids/1055399359.png" alt="shut up">
			</figure>
		</article>
	</secion>

	<secion class="snap-center w-screen h-[100vh] flex items-center justify-center">
		<article class="max-w-3xl p-4 flex justify-evenly">
			<figure class="group max-w-xs hover:border-2 p-4 rounded-full relative transition-all">
				<h3 class="transition-all opacity-0 group-hover:opacity-100 absolute uppercase text-white underline underline-offset-4 -left-[116px] -top-[34px]">Black Hole</h3>
				<span class="transition-all opacity-0 group-hover:opacity-100 absolute w-20 border-b-2 rotate-45 -left-[21px]"></span>
				<img class="w-full" src="/images/planets/black_hole.gif" alt="shut up">
			</figure>
	
			<figure class="group w-[10%] h-[10%] self-center hover:border-2 rounded-full relative transition-all">
				<h3 class="transition-all opacity-0 group-hover:opacity-100 absolute uppercase text-white underline underline-offset-4 left-[94px] -top-[60px]">Some asteroid</h3>
				<span class="transition-all opacity-0 group-hover:opacity-100 absolute w-10 border-b-2 -rotate-45 left-[60px]"></span>
				<img class="w-full" src="/images/asteroids/3143726123.png" alt="shut up">
			</figure>
		</article>
	</secion>

	<secion class="snap-center w-screen h-[100vh] flex items-center justify-center">
		<article class="max-w-3xl p-4 flex justify-evenly">
			<figure class="group max-w-xs hover:border-2 p-4 rounded-full relative transition-all">
				<h3 class="transition-all opacity-0 group-hover:opacity-100 absolute uppercase text-white underline underline-offset-4 -left-[85px] -top-[34px]">Quadøc</h3>
				<span class="transition-all opacity-0 group-hover:opacity-100 absolute w-20 border-b-2 rotate-45 -left-[21px]"></span>
				<img class="w-full" src="/images/planets/gas_giant.gif" alt="shut up">
			</figure>
	
			<figure class="group w-[10%] h-[10%] self-center hover:border-2 rounded-full relative transition-all">
				<h3 class="transition-all opacity-0 group-hover:opacity-100 absolute uppercase text-white underline underline-offset-4 left-[94px] -top-[60px]">Some asteroid</h3>
				<span class="transition-all opacity-0 group-hover:opacity-100 absolute w-10 border-b-2 -rotate-45 left-[60px]"></span>
				<img class="w-full" src="/images/asteroids/2708503554.png" alt="shut up">
			</figure>
		</article>
	</secion>
</section>


<style>
	.star-background {
		background-image: url(/images/star_background.png), linear-gradient(#0d1f1d, #210a1e);
		background-size: 35%;
	}
</style>
