<p align="center">
  <a href="https://lingo.dev">
    <img src="https://raw.githubusercontent.com/lingodotdev/lingo.dev/main/content/banner.compiler.png" width="100%" alt="Lingo.dev" />
  </a>
</p>

<p align="center">
  <strong>⚡ Lingo.dev - විවෘත මූලාශ්‍ර, AI බලගැන්වූ i18n toolkit එකක් — LLMs භාවිතයෙන්ක් අත්‍යවශ්‍ය පරිවර්තන තත්ක්ෂණයකින්.</strong>
</p>

<br />

<p align="center">
  <a href="https://lingo.dev/compiler">Lingo.dev Compiler</a> •
  <a href="https://lingo.dev/cli">Lingo.dev CLI</a> •
  <a href="https://lingo.dev/ci">Lingo.dev CI/CD</a> •
  <a href="https://lingo.dev/sdk">Lingo.dev SDK</a>
</p>

<p align="center">
  <a href="https://github.com/lingodotdev/lingo.dev/actions/workflows/release.yml">
    <img src="https://github.com/lingodotdev/lingo.dev/actions/workflows/release.yml/badge.svg" alt="Release" />
  </a>
  <a href="https://github.com/lingodotdev/lingo.dev/blob/main/LICENSE.md">
    <img src="https://img.shields.io/github/license/lingodotdev/lingo.dev" alt="License" />
  </a>
  <a href="https://github.com/lingodotdev/lingo.dev/commits/main">
    <img src="https://img.shields.io/github/last-commit/lingodotdev/lingo.dev" alt="Last Commit" />
  </a>
  <a href="https://lingo.dev/en">
    <img src="https://img.shields.io/badge/Product%20Hunt-%231%20DevTool%20of%20the%20Month-orange?logo=producthunt&style=flat-square" alt="Product Hunt #1 DevTool of the Month" />
  </a>
  <a href="https://lingo.dev/en">
    <img src="https://img.shields.io/badge/Product%20Hunt-%231%20Product%20of%20the%20Week-orange?logo=producthunt&style=flat-square" alt="Product Hunt #1 DevTool of the Week" />
  </a>
  <a href="https://lingo.dev/en">
    <img src="https://img.shields.io/badge/Product%20Hunt-%232%20Product%20of%20the%20Day-orange?logo=producthunt&style=flat-square" alt="Product Hunt #2 Product of the Day" />
  </a>
  <a href="https://lingo.dev/en">
    <img src="https://img.shields.io/badge/GitHub-Trending-blue?logo=github&style=flat-square" alt="Github trending" />
  </a>
</p>

---

## Compiler එකට හමු වන්න 🆕

**Lingo.dev Compiler** යනු React apps multilingual කිරීම build-time දී සිදුකරන, සම්පූර්ණයෙන්ම විවෘත මූලාශ්‍ර middleware compiler එකක්.  
React components කිසිවෙකුත් වෙනස් නොකර — ඔබේ project එක බහුභාෂාගත (multilingual) කරයි.

එකවර install කරන්න:

```bash
npm install lingo.dev
```

Build config එකේ enable කරන්න:

```js
import lingoCompiler from "lingo.dev/compiler";

const existingNextConfig = {};

export default lingoCompiler.next({
  sourceLocale: "en",
  targetLocales: ["es", "fr"],
})(existingNextConfig);
```

ඊට පසුව `next build` ක්‍රියාත්මක කරන්න — Spanish සහ French builds magically generate වෙයි ✨

සම්පූර්ණ මාර්ගෝපදේශය සඳහා [docs කියවන්න →](https://lingo.dev/compiler)  
සහ ඔබට උදව් අවශ්‍ය නම් [Discord එකට එක්වන්න](https://lingo.dev/go/discord).

---

### මෙය repo එක තුලදී තියෙන්නේ?

| මෙවලම        | කෙටි විස්තර                                            | ලේඛන                                    |
| ------------ | ------------------------------------------------------ | --------------------------------------- |
| **Compiler** | Build-time React localization                          | [/compiler](https://lingo.dev/compiler) |
| **CLI**      | Web & mobile apps සඳහා එකම command එකකින් localization | [/cli](https://lingo.dev/cli)           |
| **CI/CD**    | Push එකකින් පසුව auto-commit + pull requests           | [/ci](https://lingo.dev/ci)             |
| **SDK**      | Dynamic content real-time translation                  | [/sdk](https://lingo.dev/sdk)           |

පහලින් tool එකකට tool එක quick summary තියෙනවා 👇

---

### ⚡️ Lingo.dev CLI

ඔබේ terminal එකෙන්ම code & content translate කරන්න.

```bash
npx lingo.dev@latest run
```

මෙය string fingerprinting, caching, සහ incremental translation logic භාවිතා කරයි.

Setup ගැන දැනගැනීමට [docs බලන්න →](https://lingo.dev/cli).

---

### 🔄 Lingo.dev CI/CD

පරිපූර්ණ පරිවර්තන ස්වයංක්‍රීයව deploy කරන්න.

```yaml
# .github/workflows/i18n.yml
name: Lingo.dev i18n
on: [push]

jobs:
  i18n:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: lingodotdev/lingo.dev@main
        with:
          api-key: ${{ secrets.LINGODOTDEV_API_KEY }}
```

මෙය repo එක හරිත තත්වයේ (green) තබා ගෙන product එක multilingual කරයි — කිසිදු manual step එකක් නැතුව.

[Docs →](https://lingo.dev/ci)

---

### 🧩 Lingo.dev SDK

Dynamic user content සඳහා real-time translation.

```ts
import { LingoDotDevEngine } from "lingo.dev/sdk";

const lingoDotDev = new LingoDotDevEngine({
  apiKey: "your-api-key-here",
});

const content = {
  greeting: "Hello",
  farewell: "Goodbye",
  message: "Welcome to our platform",
};

const translated = await lingoDotDev.localizeObject(content, {
  sourceLocale: "en",
  targetLocale: "es",
});
```

ඒක chat apps, live comments, message feeds වැනි real-time flows සඳහා සුපිරි.

[Docs බලන්න →](https://lingo.dev/sdk)

---

## 🤝 ප්‍රජාව

අපි community-driven. ඔබගේ දායකත්වය අපිට ප්‍රියයි!

- අදහසක් ද? [Issue එකක් විවෘත කරන්න](https://github.com/lingodotdev/lingo.dev/issues)
- කිසිවක් සෙමි කරන්නද? [PR එකක් යවන්න](https://github.com/lingodotdev/lingo.dev/pulls)
- උදව් එකක් ඕනේද? [Discord එකට එන්න](https://lingo.dev/go/discord)

---

## ⭐ තාරා ඉතිහාසය

ඔබට Lingo.dev සතුටුද? ⭐ එකක් දෙන්න!  
අපිට 4,000 stars இலக்கு ජයගන්න උදව් කරන්න 🌟

[![Star History Chart](https://api.star-history.com/svg?repos=lingodotdev/lingo.dev&type=Date)](https://www.star-history.com/#lingodotdev/lingo.dev&Date)

---

## 🌐 වෙනත් භාෂා පිටපත්

[English](https://github.com/lingodotdev/lingo.dev) • [中文](/readme/zh-Hans.md) • [日本語](/readme/ja.md) • [한국어](/readme/ko.md) • [Español](/readme/es.md) • [Français](/readme/fr.md) • [Русский](/readme/ru.md) • [Українська](/readme/uk-UA.md) • [Deutsch](/readme/de.md) • [Italiano](/readme/it.md) • [العربية](/readme/ar.md) • [עברית](/readme/he.md) • [हिन्दी](/readme/hi.md) • [বাংলা](/readme/bn.md) • [فارسی](/readme/fa.md)

ඔබගේ භාෂාව නොපෙනෙනවද? [`i18n.json`](./i18n.json) හි එකතු කර PR එකක් විවෘත කරන්න!
