<template>
	<div>
		<span>{{ node.name }}</span>
		<ul v-if="node.children && node.children.length > 0">
			<li v-for="(item, index) in node.children" :key="item.name + index">
				<tree :node="item"></tree>
			</li>
		</ul>
	</div>
</template>

<script>
export default {
	props: ["node"],
	name: "tree",
};
</script>