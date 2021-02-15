<template>
	<div>
		<TreeChart v-if="1 == 2" :json="treeData" />
		<ul class="tree">
			<li>
				<tree :node="treeData"></tree>
			</li>
		</ul>
	</div>
</template>

<script>
import TreeChart from "vue-tree-chart";
import Tree from "../components/TreeComponent";
export default {
	components: {
		TreeChart,
		Tree,
	},

	data() {
		return {
			treeData: {
				name: "root",
				image_url: "https://picsum.photos/400/400",
				class: ["rootNode"],
				children: [
					{
						name: "children1",
						image_url: "https://picsum.photos/200/200",
						children: [
							{
								name: "grandchild",
								image_url: "https://picsum.photos/400/400",
								children: [
									{
										name: "grandchild",
										image_url: "https://picsum.photos/400/400",
									},
									{
										name: "grandchild2",
										image_url: "https://picsum.photos/200/200",
									},
								],
							},
							{
								name: "grandchild2",
								image_url: "https://picsum.photos/200/200",
							},
						],
					},
					{
						name: "children2",
						image_url: "https://static.refined-x.com/avat2.jpg",
						mate: [
							{
								name: "mate",
								image_url: "https://static.refined-x.com/avat3.jpg",
							},
						],
						children: [
							{
								name: "grandchild",
								image_url: "https://picsum.photos/400/400",
							},
							{
								name: "grandchild2",
								image_url: "https://picsum.photos/200/200",
							},
						],
					},
				],
			},
		};
	},
};
</script>