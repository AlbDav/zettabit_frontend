<template>
	<div id="editor">
	</div>
</template>

<script>
import { baseKeymap } from 'prosemirror-commands';
import { undo, redo, history } from 'prosemirror-history';
import { keymap } from 'prosemirror-keymap';
import { schema } from 'prosemirror-schema-basic';
import { EditorState } from 'prosemirror-state';
import { EditorView } from 'prosemirror-view';

export default {
	mounted() {
		this.initializeEditor();
	},
	methods: {
		initializeEditor() {
			const state = EditorState.create({
				schema,
				plugins: [
					history(),
					keymap({ 'Mod-z': undo, 'Mod-Z': redo }),
					keymap(baseKeymap),
				],
			});
			const view = new EditorView(document.querySelector('#editor'), { state });
		},
	},
};
</script>
