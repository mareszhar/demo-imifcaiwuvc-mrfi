# Minimal Repo Demonstrating Issue

---

Issue: Missing intellisense for components auto-imported with unplugin-vue-components.

---

## Details

`npm run dev` runs without issues. But, if you hover over the auto-imported `HelloWorld` component in
`App.vue`, you will see that intellisense is missing.

Changing the module name in `components.d.ts` from `'@vue/runtime-core'` to `'vue'` somehow fixes the issue.

But, the problem is that manually changing the module name in `components.d.ts` is not sustainable.
Whenever the `unplugin-vue-components` detects a change in the components directory, it automatically
updates the definitions file and changes the module name back to `'@vue/runtime-core'`.
