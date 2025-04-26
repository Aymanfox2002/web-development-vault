


## 🧠 What is Code Splitting?

**Code Splitting** is a performance optimization technique where the JavaScript code is broken into **smaller bundles (chunks)** that are loaded **only when needed**, instead of loading the entire app at once.

> 📦 This leads to **faster initial page loads** and **better user experience**.

---

## ⚙️ How Code Splitting Works in Next.js

Next.js performs **automatic code splitting** out of the box for each page in the `/pages` or `/app` directory.

- Every page becomes its own JS chunk.
    
- Shared code is extracted into common chunks.
    

✅ **You don’t need to configure anything manually for this basic behavior.**

---

## ✨ When to Use Manual Code Splitting?

Sometimes you want to **delay loading** of heavy components (charts, maps, etc.) until they're visible. That’s where **manual (dynamic) code splitting** comes in.

---

## 🛠️ How to Do Manual Code Splitting

You use **`next/dynamic`** to dynamically import components.

```javascript
import dynamic from "next/dynamic";

// This component will only be loaded when rendered
const Chart = dynamic(() => import("../components/Chart"));

export default function Dashboard() {
  return (
    <div>
      <h1>Dashboard</h1>
      <Chart /> {/* Loaded only here */}
    </div>
  );
}
```

---

## ⏳ Adding a Loading Spinner

You can add a loading state while the chunk is being fetched:

```js
const Chart = dynamic(() => import("../components/Chart"), {
  loading: () => <p>Loading chart...</p>,
});
```

---

## 🧩 Real-Life Use Cases

|Component|When to Split?|
|---|---|
|Charts/Graphs|Used on one page only|
|Maps (Leaflet, Google Maps)|Heavy libraries, rarely used|
|Modals|Optional UI not always visible|
|Editors (e.g., rich text editors)|Used on special pages|

---

## ⚡ Bonus: Split Libraries Too!

If a library like **Moment.js** or **Chart.js** is big, load it only where needed:

```js
const moment = await import("moment");
```

---

## ✅ Benefits of Code Splitting

- 🚀 Faster initial load
    
- 📉 Smaller bundle sizes
    
- 🧠 Better user experience
