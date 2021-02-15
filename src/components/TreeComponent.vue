<template>
	<a href="">
		<div class="child_box">
			<img :src="node.image_url" alt="" />
			<span>{{ node.name }}</span>
		</div>
        <div class="box_popup">
			<p>Total: 100</p>
			<p>Age: 100</p>
			<p>Score: 100</p>
			<p>Point: 100</p>
			<p>Radius: 100</p>
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