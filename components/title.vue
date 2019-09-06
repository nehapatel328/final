<template>
 <article class="card">
	 <h2 class="card">{{ title.name }}</h2>
	 <p class="card">{{ title.publisher }}</p>
   <p class="card">{{ title.ranks_history }}</p>
   <p class="card">{{ title.isbn }}</p>
   <p class="card">{{ title.description }}</p>
 </article>
</template>

<script>
export default {
	props: {
		title: Object
	}
}
</script>
