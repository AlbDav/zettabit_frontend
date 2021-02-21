<template>
    <article-node :type="node.type" :marks="node.marks">
        <template v-if="node.content">
            <article-render v-for="(subNode, i) in node.content" :key="i" :node="subNode">
            </article-render>
        </template>
        <template v-else>
            {{ node.text }}
        </template>
    </article-node>
</template>

<script>
import ArticleNode from '../components/Article/ArticleNode.vue';
import ArticleNode from './ArticleNode.vue';

export default {
    name: 'article-render',
    props: ['node'],
    components: {
        ArticleNode
    }
}
</script>