<template>
  <div>
    <div>{{ data }}</div>
    <Editor @updateData="handleUpdateData" />

    <br />
    <div v-html="data"></div>
  </div>
</template>

<script>
import Editor from "./EditorVue.vue";
import edjsParser from "editorjs-parser";
// import edjsHTML from "editorjs-html";

export default {
  data: () => ({
    data: {},
    extingData: {
      time: 1640843780552,
      blocks: [
        {
          id: "yWoi-eeNHP",
          type: "header",
          data: {
            text: "Editor.js",
            level: 2,
          },
        },
        {
          id: "bbBg320Qpg",
          type: "paragraph",
          data: {
            text: "Hey. Meet the new Editor. On this page you can see it in action — try to edit this text.",
          },
        },
        {
          id: "YtvhYwijlA",
          type: "header",
          data: {
            text: "Key features",
            level: 3,
          },
        },
        {
          id: "smBdxygUFM",
          type: "list",
          data: {
            style: "unordered",
            items: [
              "It is a block-styled editor",
              "It returns clean data output in JSON",
              "Designed to be extendable and pluggable with a simple API",
            ],
          },
        },
        {
          id: "Am-JPnVewJ",
          type: "embed",
          data: {
            service: "youtube",
            source: "https://www.youtube.com/watch?v=TVLURx2nFqw",
            embed: "https://www.youtube.com/embed/TVLURx2nFqw",
            width: 580,
            height: 320,
            caption: "",
          },
        },
        {
          id: "iVHlHaCgxt",
          type: "header",
          data: {
            text: "What does it mean «block-styled editor»",
            level: 3,
          },
        },
        {
          id: "Nt7uMDHpFf",
          type: "paragraph",
          data: {
            text: 'Workspace in classic editors is made of a single contenteditable element, used to create different HTML markups. Editor.js <mark class="cdx-marker">workspace consists of separate Blocks: paragraphs, headings, images, lists, quotes, etc</mark>. Each of them is an independent contenteditable element (or more complex structure) provided by Plugin and united by Editor\'s Core.',
          },
        },
        {
          id: "R84qIDBr4I",
          type: "paragraph",
          data: {
            text: 'There are dozens of <a href="https://github.com/editor-js">ready-to-use Blocks</a> and the <a href="https://editorjs.io/creating-a-block-tool">simple API</a> for creation any Block you need. For example, you can implement Blocks for Tweets, Instagram posts, surveys and polls, CTA-buttons and even games.',
          },
        },
        {
          id: "0NRGgI0i1M",
          type: "header",
          data: {
            text: "What does it mean clean data output",
            level: 3,
          },
        },
        {
          id: "moBn_XBtXo",
          type: "paragraph",
          data: {
            text: "Classic WYSIWYG-editors produce raw HTML-markup with both content data and content appearance. On the contrary, Editor.js outputs JSON object with data of each Block. You can see an example below",
          },
        },
        {
          id: "-e73L2HsBD",
          type: "paragraph",
          data: {
            text: 'Given data can be used as you want: render with HTML for <code class="inline-code">Web clients</code>, render natively for <code class="inline-code">mobile apps</code>, create markup for <code class="inline-code">Facebook Instant Articles</code> or <code class="inline-code">Google AMP</code>, generate an <code class="inline-code">audio version</code> and so on.',
          },
        },
        {
          id: "53ZMEk6Evu",
          type: "paragraph",
          data: {
            text: "Clean data is useful to sanitize, validate and process on the backend.",
          },
        },
        {
          id: "bQUahlbWnN",
          type: "delimiter",
          data: {},
        },
        {
          id: "ekgMvb49vo",
          type: "paragraph",
          data: {
            text: "We have been working on this project more than three years. Several large media projects help us to test and debug the Editor, to make it's core more stable. At the same time we significantly improved the API. Now, it can be used to create any plugin for any task. Hope you enjoy. 😏",
          },
        },
        {
          id: "xaTNGB--z7",
          type: "image",
          data: {
            file: {
              url: "https://codex.so/public/app/img/external/codex2x.png",
            },
            caption: "",
            withBorder: false,
            stretched: false,
            withBackground: false,
          },
        },
        {
          id: "pMkHDWIO3g",
          type: "image",
          data: {
            file: {
              url: "/upload/redactor_images/o_b34af3853a25681eb03123eecf99953f.jpg",
              width: 2880,
              height: 1800,
            },
            caption: "",
            withBorder: false,
            stretched: false,
            withBackground: false,
          },
        },
      ],
      version: "2.22.2",
    },
  }),
  components: {
    Editor,
  },
  methods: {
    handleUpdateData(data) {
      const parser = new edjsParser();
      console.log("calling");
      console.log(
        "✈ ✈ ✈ ✈ ✈ ✈ ✈ ✈ ✈ ✈ ✈ ✈ ✈ ✈ ✈ ✈ ✈ ✈ ✈ ✈ ✈ ✈ ✈ tag",
        parser.parse(data)
      );
      this.$data.data = `${parser.parse(data)}------${parser.parse(
        this.$data.extingData
      )}`;
    },
  },
};
</script>

<style scoped></style>
