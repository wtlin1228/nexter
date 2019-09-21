# Nexter

Pure HTML/CSS project, use lots of **Grid**

### 設定 Grid Template Rows
`grid-template-rows: 80vh min-content 40vw repeat(3, min-content);`

我們先把垂直軸切成六塊，分別給 sidebar, header, realtors, features, story, homes, gallery, footer 用。

這邊的 min-content 指的是，這一個 Row 的高度一定會包住內容，所以 realtors, story, homes, gallery, footer 這幾個都使用這一個設定。

### 設定 Grid Template Columns
`grid-template-columns: 0.8rem 1fr repeat(8, minmax(min-content, 1.4rem)) 1fr;`

因為我把 font-size 設成 625% 也就是 100px，所以 `0.8rem` 就是 80px，第一個 column 就是用來放 sidebar 用的，直接給一個固定的寬度。

中間使用 `repeat(8, minmax(min-content, 1.4rem))` 是因為我們右邊的 layout 可以直接用這八格來做。

其中有兩個 `1fr` 是為了讓主要的八格可以置中，並且如果想要用全寬的 layout 的時候可以只用這左右兩個來達成。

### 棒棒的連結
+ 直接用 GUI 拉 GRID https://grid.layoutit.com/