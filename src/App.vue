<template>
  <editor-content :editor="editor" />
</template>

<script>
import { Editor, EditorContent } from "@tiptap/vue-2";
import StarterKit from "@tiptap/starter-kit";

export default {
  components: {
    EditorContent,
  },

  data() {
    return {
      editor: null,
    };
  },

  mounted() {
    this.editor = new Editor({
      extensions: [StarterKit],
      content: `
        <pre><code>
	Please copy and paste the moby content from the long example here.
	</code></pre>
      `,
    });
  },

  beforeUnload() {
    this.editor.destroy();
  },
};
</script>
