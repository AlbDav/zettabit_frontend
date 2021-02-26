<template>
	<div v-if="type === 'doc'">
		<slot></slot>
	</div>
  <p v-else-if="type === 'paragraph'">
    <slot></slot>
  </p>
  <h1 v-else-if="type === 'heading'">
    <slot></slot>
  </h1>
  <span v-else>
	<slot>
	</slot>
  </span>
</template>

<script>
export default {
	props: ['type', 'marks'],
};
</script>
