<template>
	<view class="demo-toast">
		<cl-toast ref="toast"></cl-toast>

		<cl-card label="文字提示">
			<cl-button @tap="open('文字提示')">
				<text>文字提示</text>
			</cl-button>
			<cl-button @tap="open('这是一条长文字提示，超过一定字数就会换行')">
				<text>长文字提示</text>
			</cl-button>
		</cl-card>

		<cl-card label="不同位置">
			<cl-button @tap="openPosition('top')">
				<text>顶部</text>
			</cl-button>
			<cl-button @tap="openPosition('middle')">
				<text>居中</text>
			</cl-button>
			<cl-button @tap="openPosition('bottom')">
				<text>底部</text>
			</cl-button>
		</cl-card>

		<cl-card label="不同状态">
			<cl-button @tap="openType('default')">
				<text>默认</text>
			</cl-button>
			<cl-button @tap="openType('primary')">
				<text>主要</text>
			</cl-button>
			<cl-button @tap="openType('success')">
				<text>成功</text>
			</cl-button>
			<cl-button @tap="openType('error')">
				<text>失败</text>
			</cl-button>
			<cl-button @tap="openType('warning')">
				<text>警告</text>
			</cl-button>
		</cl-card>

		<cl-card label="带图标">
			<cl-button type="success" @tap="openIcon('success')">
				<text>success</text>
			</cl-button>
			<cl-button type="error" @tap="openIcon('error')">
				<text>error</text>
			</cl-button>
			<cl-button type="warning" @tap="openIcon('warning')">
				<text>warning</text>
			</cl-button>
		</cl-card>
	</view>
</template>

<script>
export default {
	data() {
		return {
			loading: true
		};
	},

	methods: {
		open(message) {
			this.$refs["toast"].open(message);
		},

		openPosition(position) {
			this.$refs["toast"].open({
				position,
				message: "消息提示"
			});
		},

		openType(type) {
			this.$refs["toast"].open({
				type,
				message: "消息提示"
			});
		},

		openIcon(icon) {
			this.$refs["toast"].open({
				icon,
				position: "middle",
				message: "消息提示"
			});
		}
	}
};
</script>
