<template>
	<div class="markdown-preview">
		<interface-input-rich-text-md v-if="!disabled" :disabled="disabled" :value="value"  v-bind="attrs" v-on="listeners"  />
		<div v-else >
			<div v-if="value" v-md="value" class="preview-box" :style="'display:block'"></div>
		</div>
	</div>
	
</template>

<script>
export default {
	props: {
		value: {
			type: String,
			default: null,
		},
		disabled: {
			type: Boolean,
			default: false,
		},
	},
	setup(props, { emit, attrs, listeners }) {
		return { attrs, listeners};
	},
};
</script>
<style lang="css" scoped>
.preview-box {
	display: none;
	padding: 20px;
}

.preview-box :deep(h1) {
	margin-top: 1em;
	margin-bottom: 0;
	color: var(--foreground-normal-alt);
	font-weight: 700;
	font-size: 36px;
	font-family: v-bind(previewFamily), serif;
	line-height: 46px;
}

.preview-box :deep(h2) {
	margin-top: 1.25em;
	margin-bottom: 0;
	color: var(--foreground-normal-alt);
	font-weight: 700;
	font-size: 24px;
	font-family: v-bind(previewFamily), serif;
	line-height: 34px;
}

.preview-box :deep(h3) {
	margin-top: 1.25em;
	margin-bottom: 0;
	color: var(--foreground-normal-alt);
	font-weight: 700;
	font-size: 19px;
	font-family: v-bind(previewFamily), serif;
	line-height: 29px;
}

.preview-box :deep(h4) {
	margin-top: 1.5em;
	margin-bottom: 0;
	color: var(--foreground-normal-alt);
	font-weight: 700;
	font-size: 16px;
	font-family: v-bind(previewFamily), serif;
	line-height: 26px;
}

.preview-box :deep(h5) {
	margin-top: 2em;
	margin-bottom: 0;
	color: var(--foreground-normal-alt);
	font-weight: 700;
	font-size: 14px;
	font-family: v-bind(previewFamily), serif;
	line-height: 24px;
}

.preview-box :deep(h6) {
	margin-top: 2em;
	margin-bottom: 0;
	color: var(--foreground-normal-alt);
	font-weight: 700;
	font-size: 12px;
	font-family: v-bind(previewFamily), serif;
	line-height: 22px;
}

.preview-box :deep(p) {
	margin: 1.5em 0;
	font-weight: 500;
	font-size: 15px;
	font-family: v-bind(previewFamily), serif;
	line-height: 24px;
}

.preview-box :deep(a) {
	color: var(--primary-125);
	text-decoration: none;
}

.preview-box :deep(ul),
.preview-box :deep(ol) {
	margin: 1.5em 0;
	font-weight: 500;
	font-size: 15px;
	font-family: v-bind(previewFamily), serif;
	line-height: 24px;
}

.remaining {
	position: absolute;
	right: 10px;
	bottom: 5px;
	color: var(--foreground-subdued);
	font-weight: 600;
	text-align: right;
	vertical-align: middle;
	font-feature-settings: 'tnum';
}

.warning {
	color: var(--warning);
}

.danger {
	color: var(--danger);
}

.preview-box :deep(ul ul),
.preview-box :deep(ol ol),
.preview-box :deep(ul ol),
.preview-box :deep(ol ul) {
	margin: 0;
}

.preview-box :deep(b),
.preview-box :deep(strong) {
	font-weight: 700;
}

.preview-box :deep(code) {
	padding: 2px 4px;
	font-weight: 500;
	font-size: 15px;
	font-family: var(--family-monospace), monospace;
	line-height: 24px;
	overflow-wrap: break-word;
	background-color: var(--background-normal);
	border-radius: var(--border-radius);
}

.preview-box :deep(pre) {
	padding: 1em;
	overflow: auto;
	font-weight: 500;
	font-size: 15px;
	font-family: var(--family-monospace), monospace;
	line-height: 24px;
	background-color: var(--background-normal);
	border-radius: var(--border-radius);
}

.preview-box :deep(blockquote) {
	margin-left: 0px;
	padding-left: 1em;
	font-weight: 500;
	font-size: 15px;
	font-family: v-bind(previewFamily), serif;
	line-height: 24px;
	border-left: 2px solid var(--border-normal);
}

.preview-box :deep(blockquote blockquote) {
	margin-left: 10px;
}

.preview-box :deep(video),
.preview-box :deep(iframe),
.preview-box :deep(img) {
	max-width: 100%;
	height: auto;
	border-radius: var(--border-radius);
}

.preview-box :deep(hr) {
	height: 1px;
	margin-top: 2em;
	margin-bottom: 2em;
	background-color: var(--border-normal);
	border: none;
}

.preview-box :deep(table) {
	font-weight: 500;
	font-size: 15px;
	line-height: 24px;
	border-collapse: collapse;
}

.preview-box :deep(table th),
.preview-box :deep(table td) {
	padding: 0.4rem;
	border: 1px solid var(--border-normal);
}

.preview-box :deep(figure) {
	display: table;
	margin: 1rem auto;
}

.preview-box :deep(figure figcaption) {
	display: block;
	margin-top: 0.25rem;
	color: #999;
	text-align: center;
}

</style>

