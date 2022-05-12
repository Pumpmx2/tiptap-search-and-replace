# Tiptap 2 Search and Replace

Example of using SearchNReplace extension for [Tiptap 2](https://tiptap.dev). The repo for npm package [is here](https://github.com/sereneinserenade/tiptap-extension-search-n-replace) and here's the [link to npm package](https://www.npmjs.com/package/@sereneinserenade/tiptap-extension-search-n-replace).

If you **👍 / ❤️ what I'm doing**, consider **🌟ing the repo**, **I** and the **Open-Source-Community** appreciate it very much ❤️.


# Live Demo

Try it out live at https://sereneinserenade.github.io/tiptap-search-n-replace-demo, and/or take a look at a demo-video below.

<details> 
  <summary> <b>demo-video</b> </summary>
  
https://user-images.githubusercontent.com/45892659/163356581-5fd38888-4e29-41d9-b64f-d17948ef7a16.mov
</details>

## How to use

I've published it as an [npm package](https://www.npmjs.com/package/@sereneinserenade/tiptap-extension-search-n-replace) so you can either directly install it, 
 
<details>
  <summary> with NPM </summary>

```
npm i @sereneinserenade/tiptap-extension-search-n-replace
```
</details>
<details>
  <summary> with Yarn </summary>

```
yarn add @sereneinserenade/tiptap-extension-search-n-replace
```
</details>

**or you can just** copy-paste [`search.ts`](src/components/search.ts) file in your own repo and import `SearchNReplace` from that file and use that as an extension. For more details see [`Tiptap.vue`](src/components/Tiptap.vue#L50-L88) or the example implementations below.


### Here are example implementations in Vue and React

<details>
  <summary> Vue </summary>

```ts
import { Editor } from "@tiptap/core";
import { SearchNReplace } from "./path/to/search-n-replace.ts/";

const editor = new Editor({
  content: "<p>Example Text</p>",
  extensions: [
    SearchNReplace.configure({
      searchResultClass: "search-result", // class to give to found items. default 'search-result'
      caseSensitive: false, // no need to explain
      disableRegex: false, // also no need to explain
    }),
  ],
});

const searchTerm = ref<string>("replace");

const replaceTerm = ref<string>("astonishing");

// you can use the commands provided by SearchNReplace extension to update the values of search and replace terms.
const updateSearchReplace = () => {
  if (!editor.value) return;
  editor.value.commands.setSearchTerm(searchTerm.value);
  editor.value.commands.setReplaceTerm(replaceTerm.value);
};
```
</details>
  
<details>
  <summary> React </summary>

```ts
import { Editor } from "@tiptap/core";
import { SearchNReplace } from "./path/to/search-n-replace.ts/";

const editor = new Editor({
  content: "<p>Example Text</p>",
  extensions: [
    SearchNReplace.configure({
      searchResultClass: "search-result", // class to give to found items. default 'search-result'
      caseSensitive: false, // no need to explain
      disableRegex: false, // also no need to explain
    }),
  ],
});

const searchTerm = useState<string>("replace");

const replaceTerm = useState<string>("astonishing");

// you can use the commands provided by SearchNReplace extension to update the values of search and replace terms.
const updateSearchReplace = () => { // you can probably use `useCallback` hook)
  if (!editor.value) return;
  editor.value.commands.setSearchTerm(searchTerm.value);
  editor.value.commands.setReplaceTerm(replaceTerm.value);
};
```
</details>



## Contributing

Show your ❤️ by ⭐️ing this repository! It means a lot.

Clone the repo, do something, make a PR(or not). You know what's the drill. Looking forward to your PRs, you amazing devs.

## Awesome peeps, who've starred this repo 🚀! Thank you!
[![Stargazers repo roster for @sereneinserenade/tiptap-search-n-replace-demo](https://reporoster.com/stars/dark/sereneinserenade/tiptap-search-n-replace-demo)](https://github.com/sereneinserenade/tiptap-search-n-replace-demo/stargazers)

---

<details>
  <summary> Stuff that nobody really cares about </summary>

  # Vue 3 + Vite

  This template should help get you started developing with Vue 3 in Vite. The template uses Vue 3 `<script setup>` SFCs, check out the [script setup docs](https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup) to learn more.

  ## Recommended IDE Setup

  - [VS Code](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=johnsoncodehk.volar)
</details>
