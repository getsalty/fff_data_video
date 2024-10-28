---
theme: [air, near-midnight, wide, alt]
title: FFF report
toc: false
---

# Income and Population charts of my country

```js
const nations = FileAttachment("./data/nations.json").json();
```

```js
function launchTimeline(title, stroke, data, { width } = {}) {
  return Plot.plot({
    title: title,
    width,
    height: 300,
    y: { grid: true, label: title },
    marks: [Plot.dot(data, { stroke: stroke })],
  });
}
```

<div class="grid grid-cols-2">
  <div class="card">${resize((width) => launchTimeline("Income", "red", nations.find((nation) => nation.name === "United States").income, {width}))}</div> 
  <div class="card">${resize((width) => launchTimeline("Population", "blue", nations.find((nation) => nation.name === "United States").population, {width}))}</div>
</div>

<!-- <div class="grid grid-cols-1">
  <div class="card">
    ${JSON.stringify(nations)}
  </div>
</div> -->
