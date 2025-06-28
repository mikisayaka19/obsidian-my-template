---
notetoolbar: home
tags:
  - moc
CreatedDate: 2025-02-09
cssclasses:
  - no-properties
---
```dataviewjs
// Calculate days since first note
const files = dv.pages()
const oldestFile = files.sort(f => f.file.ctime)[0]
const daysSinceStart = Math.floor((Date.now() - oldestFile.file.ctime) / (1000 * 60 * 60 * 24))
// Count total notes
const totalNotes = files.length
// Create a visually appealing display that works in both light and dark modes
dv.paragraph(`<div style="
  background-color: var(--background-secondary);
  border: 1px solid var(--background-modifier-border);
  border-radius: 10px;
  padding: 20px;
  text-align: center;
  font-family: var(--font-text);
  color: var(--text-normal);
">
  <h2 style="color: var(--text-normal);">🏡Obsidian HOME🏡</h2>
  <p style="font-size: 18px; margin: 5px 0;">
    🗓️ 今日は、obsidianを使いはじめて <strong>${daysSinceStart}</strong> 日目です。  📝 現在、 <strong>${totalNotes}</strong> 個のnoteがあります。
  </p>
</div>`)
```
---
>[!multi-column]
>> [!note]+ MOC-main
>> 👉 [[00_Projectまとめ]]
>> 🛡️ [[10_XXXXXまとめ]]
>> 🗓️ [[25_timesまとめ]]
>> 📝 [[00_エビデンス集]]
>> 🌐 [[00_Webクリップ集]]
>
>> [!tip]+ MOC-sub
>> 💻 [[05_技術系まとめ]]
>> 💡 [[10_Tipsまとめ]]
>> 🔍 [[15_XXXXまとめ]]
>> 🪪 [[20_環境情報]]
>> 🖊️ [[30_資格勉強]]
>
>> [!faq]+ MOC-obsidian
>> ✅ [[obsidian_Myルール]]
>> 📂 [[obsidian_Tips]]
>> 🎨 [[記法確認ページ]]
>> 🔗 [[仮1]]
>> ⚙️ [[仮2]]
>
>> [!quote]+ Memo
>> 🔧 ~~
>> 🔧 ~~
>>  
>>  
>>  

---
> [!multi-column]
>
> > [!summary]+ Recently Created
>>```dataview
> >List
> >From "01_Inbox" or "05_Canvas"  or "06_Projects" or "07_WebClipper" or "08_Evidence" 
> >sort file.ctime Desc
> >Limit 7
> >```
>
> > [!example]+ Recently Modified
>> ```dataview 
> > List 
> > From "01_Inbox" or "05_Canvas"  or "06_Projects" or "07_WebClipper" or "08_Evidence" 
> > sort file.mtime Desc
> > Limit 7
> > ```
>
> > [!check]+ Recent Projects
>> ```dataview 
> > List 
> > From "06_Projects"
> > sort file.mtime Desc
> > Limit 7
> > ```

---
> [!multi-column]
>
> > [!missing]+ リンクが存在しないページ
>>```dataview
> >List
> >From "01_Inbox" or "06_Projects" 
> >WHERE length(file.inlinks) = 0 and !contains(tags, "times")
> >sort file.ctime Desc
> >Limit 3
> >```
>
> > [!missing]+ タグが存在しないページ
>> ```dataview 
> > List 
> >From "01_Inbox" or "06_Projects" 
> >WHERE length(file.tags) = 0
> >sort file.ctime Desc
> >Limit 3
> > ```
