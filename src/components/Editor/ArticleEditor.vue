<template>
	<div id="editor"></div>
</template>

<script>
import { schema } from "prosemirror-schema-basic";
import { EditorState } from "prosemirror-state";
import { EditorView } from "prosemirror-view";

export default {
	mounted() {
		this.initializeEditor();
	},
	methods: {
		inizializeEditor() {
			let state = EditorState.create({ schema });
			let view = new EditorView(document.querySelector('#editor'), { state });
		}
	}
}
</script>