<template>
	<a href="">
		<div class="child_box">
			<img :src="node.image_url" alt="" />
			<span>{{ node.name }}</span>
		</div>
		<ul v-if="node.children && node.children.length > 0">
			<li v-for="(item, index) in node.children" :key="item.name + index">
				<tree :node="item"></tree>
			</li>
		</ul>
	</a>
</template>

<script>
export default {
	props: ["node"],
	name: "tree",
};
</script>