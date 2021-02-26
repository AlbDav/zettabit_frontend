<template>
  <div class="about">
    <h1>This is an about page</h1>
    <input type="text" class="sul-text-field" placeholder="Text">
  </div>
  <div>
    {{ content }}
  </div>
  <article-render :node="article"></article-render>
</template>

<script>
import ArticleRender from '../components/Article/ArticleRender.vue';
// import ArticleNode from '../components/Article/ArticleNode.vue';

export default {
	data() {
		return {
			article: {
				type: 'doc',
				content: [
					{
						type: 'heading',
						attrs: {
							level: 2,
						},
						content: [
							{
								type: 'text',
								text: 'Export HTML or JSON',
							},
						],
					},
					{
						type: 'paragraph',
						content: [
							{
								type: 'text',
								text: 'You are able to exp ort your data as ',
							},
							{
								type: 'text',
								marks: [
									{
										type: 'code',
									},
								],
								text: 'HTML',
							},
							{
								type: 'text',
								text: ' or ',
							},
							{
								type: 'text',
								marks: [
									{
										type: 'code',
									},
								],
								text: 'JSON',
							},
							{
								type: 'text',
								text: '.',
							},
						],
					},
				],
			},
		};
	},
	components: {
		ArticleRender,
	},
};
</script>
