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

### Emmet 生成多個 html tag 並且有初始值
`feature{feature $}*6`

會長出個這個東西

```HTML
<div class="feature">feature 1</div>
<div class="feature">feature 2</div>
<div class="feature">feature 3</div>
<div class="feature">feature 4</div>
<div class="feature">feature 5</div>
<div class="feature">feature 6</div>
```

### 不要重複的寫一樣的 CSS - selector 

```CSS
%heading {
  font-family: $font-display;
  font-weight: 400;
}

.heading-1 {
  @extend %heading;
}

.heading-2 {
  @extend %heading;
}

.heading-3 {
  @extend %heading;
}

.heading-4 {
  @extend %heading;
}
```

### 直接用 Grid 做 Responsive

在 features 裡面有六個 feature，如果想要讓 feature 自動換行，可以這樣寫

`grid-template-columns: repeat(auto-fit, minmax(2.5rem, 1fr));`

`auto-fit`： 依照我們訂的大小，自動判斷可以放幾個 track
`minmax(2.5rem, 1fr)`： 每一個 track 至少要有 250px，並且超過 250px 的時候就會平分寬度，例如 width = 800，那麼每一行就會有三個 track，每個 track 的寬度就是 (800 - 2 * grid-column-gap) / 3

### 想要在圖片上面加一層東西可以這樣

利用 `background-image` 可以接受多個參數來達成

`background-image: linear-gradient(rgba($color-primary, .5), rgba($color-primary, .5)), url(../img/back.jpg);`

### 讓圖片能夠剛好填滿整個容器

可以先把 `<img />` 放到一個 `<figure />` 裡面

`<figure class="gallery__item gallery__item--1"><img src="img/gal-1.jpeg" alt="Gallery image 1" class="gallery__img"></figure>`

然後利用 `object-fit` 就可以讓圖片剛好填滿

```CSS
width: 100%;
height: 100%;
object-fit: cover;
display: block;
```

### 棒棒的連結
+ 直接用 GUI 拉 GRID https://grid.layoutit.com/