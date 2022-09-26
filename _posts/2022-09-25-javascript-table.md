---
toc: true
layout: post
description: Making a javascript table
categories: [markdown]
title: Table for JavaScript
---

```
<div id="javascriptTable">
 
</div>
 
<script>
 
const data = ["yasha","james","quinn","aaron"]
 
let table = document.createElement("table");
let row = document.createElement("tr");
for(let i=0; i<data.length; i++){
   let td=document.createElement("td");
   let node=document.createTextNode(data[i]);
   td.appendChild(node);
   row.appendChild(td);
}
table.appendChild(row);
let div = document.getElementById("javascriptTable");
div.appendChild(table);
 
</script>

```

{% include javascript-table.html %}