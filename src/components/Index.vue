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

<style>
.tree,
.tree ul,
.tree li {
	list-style: none;
	margin: 0;
	padding: 0;
	position: relative;
}

.tree {
	margin: 0 0 1em;
	text-align: center;
}

.tree,
.tree ul {
	display: table;
}

.tree ul {
	width: 100%;
}

.tree li {
	display: table-cell;
	padding: 0.5em 0;
	vertical-align: top;
}

.tree li:before {
	outline: solid 1px #666;
	content: "";
	left: 0;
	position: absolute;
	right: 0;
	top: 0;
}

.tree li:first-child:before {
	left: 50%;
}

.tree li:last-child:before {
	right: 50%;
}

.tree code,
.tree span {
	border: solid 0.1em #666;
	border-radius: 0.2em;
	display: inline-block;
	margin: 0 0.2em 0.5em;
	padding: 0.2em 0.5em;
	position: relative;
}

.tree ul:before,
.tree code:before,
.tree span:before {
	outline: solid 1px #666;
	content: "";
	height: 0.5em;
	left: 50%;
	position: absolute;
}

.tree ul:before {
	top: -0.5em;
}

.tree code:before,
.tree span:before {
	top: -0.55em;
}

.tree > li {
	margin-top: 0;
}

.tree > li:before,
.tree > li:after,
.tree > li > code:before,
.tree > li > span:before {
	outline: none;
}
</style>
