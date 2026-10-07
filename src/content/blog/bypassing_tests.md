---
title: "Bypassing Tests"
description: "`if true`"
pubDate: "Aug 06 2026"
heroImage: "/blog-placeholder-5.jpg"
---

This is more than enough.

## Attempt Number 1

Code:
```
{/*TEST GOES HERE*/}
```

Results:
{/**
  * @typedef {Object} Props
  * @property {string} name
  */}

export function Hello({ name }) {
  return <h1>Hello, {name}</h1>;

}