```dataviewjs
let pages = dv.pages('"Dictionary"'); // dv.pages("#daily") if you use tags over folders
// Loop through pages
for (let p of pages){
  // dv.el("h2",p.file.name); // note title
  // dv.paragraph(dv.fileLink(p.file.name,false)) // link to note
  dv.el("article", await dv.io.load(p.file.path)); // note body
}
```
