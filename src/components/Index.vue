<template>
	<div>
		<ul class="tree">
			<li>
				<tree :node="treeData"></tree>
			</li>
		</ul>
	</div>
</template>

<script>
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
						image_url: "https://picsum.photos/400/400",
						mate: [
							{
								name: "mate",
								image_url: "https://picsum.photos/400/400",
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
.tree {
	width: 100%;
	height: auto;
	text-align: center;
}
.tree ul {
	padding-top: 20px;
	position: relative;
	transition: 0.5s;
}
.tree li {
	display: inline-table;
	text-align: center;
	list-style-type: none;
	position: relative;
	padding: 10px;
	transition: 0.5s;
}
.tree li::before,
.tree li::after {
	content: "";
	position: absolute;
	top: 0;
	right: 50%;
	border-top: 1px solid #ccc;
	width: 51%;
	height: 10px;
}
.tree li::after {
	right: auto;
	left: 50%;
	border-left: 1px solid #ccc;
}
.tree li:only-child::after,
.tree li:only-child::before {
	display: none;
}
.tree li:only-child {
	padding-top: 0;
}
.tree li:first-child::before,
.tree li:last-child::after {
	border: 0 none;
}
.tree li:last-child::before {
	border-right: 1px solid #ccc;
	border-radius: 0 5px 0 0;
	-webkit-border-radius: 0 5px 0 0;
	-moz-border-radius: 0 5px 0 0;
}
.tree li:first-child::after {
	border-radius: 5px 0 0 0;
	-webkit-border-radius: 5px 0 0 0;
	-moz-border-radius: 5px 0 0 0;
}
.tree ul::before {
	content: "";
	position: absolute;
	top: 0;
	left: 50%;
	border-left: 1px solid #ccc;
	width: 0;
	height: 20px;
}
.tree li .child_box {
	border: 1px solid #ccc;
	padding: 10px;
	display: inline-grid;
	border-radius: 5px;
	text-decoration-line: none;
	border-radius: 5px;
	transition: 0.5s;
}
.tree li a img {
	width: 50px;
	height: 50px;
	margin-bottom: 10px !important;
	border-radius: 100px;
	margin: auto;
}
.tree li a span {
	border: 1px solid #ccc;
	border-radius: 5px;
	color: #666;
	padding: 8px;
	font-size: 12px;
	text-transform: uppercase;
	letter-spacing: 1px;
	font-weight: 500;
}
/*Hover-Section*/
.tree li a .child_box:hover,
.tree li a .child_box:hover i,
.tree li a .child_box:hover span,
.tree li a .child_box:hover + ul li a .child_box {
	background: #c8e4f8;
	color: #000;
	border: 1px solid #94a0b4;
}
.tree li .child_box:hover + ul li::after,
.tree li .child_box:hover + ul li::before,
.tree li .child_box:hover + ul::before,
.tree li .child_box:hover + ul ul::before {
	border-color: #94a0b4;
}
</style>