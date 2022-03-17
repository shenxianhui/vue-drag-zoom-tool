# 拖动缩放组件

## 示例

![](https://gitee.com/shenxianhui/xx-static/raw/master/img/20220317-drag_demo.gif)

## 说明

该组件适用于对一个元素在某个区域内进行拖动/缩放

## 安装

```
npm i vue-drag-zoom
```

## 使用

```
<template>
	<div class="drag-zoom" ref="drag-zoom">
		<vue-drag-zoom
			:area-node="node"
			allow-zoom
			:range="0.2"
			:max-zoom="10"
			:min-zoom="0.2"
		>
			<div class="drag-zoom-content">
				该区域可随意拖动/缩放
			</div>
		</vue-drag-zoom>
	</div>
</template>

<script>
import VueDragZoom from 'vue-drag-zoom';

export default {
	components: {
		VueDragZoom,
	},
	data() {
		return {
			node: null,
		};
	},
	mounted() {
		this.node = this.$refs['drag-zoom'];
	},
};
</script>

<style scoped lang="less">
.drag-zoom {
	position: relative;
	width: 50%;
	height: 50%;
	margin: 100px auto;
	background-color: lightblue;
	overflow: hidden;
	.drag-zoom-content {
		width: 150px;
		height: 150px;
		background: #ff000099;
	}
}
</style>
```

## API

### Attributes

| 参数        | 说明                                      | 类型           | 可选值 | 默认值 |
| ----------- | ----------------------------------------- | -------------- | ------ | ------ |
| left        | 被操作的元素 X 坐标                       | number         | -      | 0      |
| top         | 被操作的元素 Y 坐标                       | number         | -      | 0      |
| width       | 被操作的元素宽度                          | number         | -      | -      |
| height      | 被操作的元素高度                          | number         | -      | -      |
| allow-zoom  | 允许缩放                                  | boolean        | true   | false  |
| zoom        | 缩放比例                                  | number         | -      | 1      |
| max-zoom    | 最大缩放比例                              | number         | -      | 2      |
| min-zoom    | 最小缩放比例                              | number         | -      | 0.5    |
| range       | 缩放幅度                                  | number         | -      | 0.1    |
| area-node   | 活动区域节点                              | HTMLDivElement | -      | -      |
| area-left   | 活动区域 X 坐标 (未设置 area-node 时生效) | number         | -      | 0      |
| area-top    | 活动区域 Y 坐标 (未设置 area-node 时生效) | number         | -      | 0      |
| area-width  | 活动区域宽度 (未设置 area-node 时生效)    | number         | -      | 200    |
| area-height | 活动区域高度 (未设置 area-node 时生效)    | number         | -      | 100    |

### Events

| 事件名      | 说明                 | 参数  |
| ----------- | -------------------- | ----- |
| mousemove   | 当鼠标拖动元素时触发 | event |
| mousescroll | 当元素缩放时触发     | event |

## 备注

有任何 bug 或优化建议, 留言至 GitHub 即可, 感谢您的使用!
