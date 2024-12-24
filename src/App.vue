

<template>
	<div class="antialiased text-gray-700 bg-gray-100">
		<div class="flex w-full h-screen justify-center items-center">
			<div class="w-full max-w-xl">
				<h1 class="text-5xl font-bold text-center text-indigo-700">Simple Quize</h1>
				<div class="bg-white p-12 rounded-lg shadow-lg w-full mt-8">
					<p class="text-2xl font-bold"></p>
				</div>
			</div>
		</div>
	</div>
	
</template>


<script setup>

</script>
<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
