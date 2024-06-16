---
title: "Syntax"
date: "2024-06-16T09:48:00-06:00"
lastmod: "2024-06-16T09:48:00-06:00"

description: "Common shortcodes and content authoring snippets"
icon: "article"
weight: 200 

draft: false 
toc: false 
---

## Shortcodes ([Full Docs](https://lotusdocs.dev/docs/shortcodes))

### Alerts ([Full Docs](https://lotusdocs.dev/docs/shortcodes/alerts))

```md
{{</* alert context="warning" icon="🍅" text="Watch out for this tomato!" */>}}
```

{{< alert text="This is the default alert. it's what you get if you don't have a context" />}}

Contexts include `info`, `success`, `danger`, `warning`, `primary`, `light` and `dark`. 

Emoji are supported - the icon can be removed with `icon=" "` 