---
title: FFF report
---

```js
const nations = FileAttachment("./data/nations.json").json();
```

```js
const color = Plot.scale({
  color: {
    type: "categorical",
    domain: d3
      .groupSort(
        nations,
        (D) => -D.length,
        (d) => d.state
      )
      .filter((d) => d !== "Other"),
    unknown: "var(--theme-foreground-muted)",
  },
});
```

<div class="grid grid-cols-1">
  <div class="card">
    ${JSON.stringify(nations)}
  </div>
</div>
