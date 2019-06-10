---
layout: post
title: Fix Multiple Chart Issue in Chart.js
---

This multiple chart issue usually happens when you hover the mouse to a coordinate that already contains existing data that was just replaced by another data returned from an asynchronous request.

## The Workaround

Suppose you have an instance of a pie chart for example:

```javascript
new Chart(context).Pie(data);
```

Assign that instance to a variable and specify that variable as a property of the `window` object like so:

```javascript
window.pieChart = new Chart(context).Pie(data);
```

Afterwards, add an `if` condition before it that checks if `window.pieChart` already exists and if so, remove it like so:

```javascript
if (window.pieChart !== undefined) {
  window.pieChart.destroy();
}

window.pieChart = new Chart(context).Pie(data);
```
