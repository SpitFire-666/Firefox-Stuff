

## Context Menu

## Font (global)

## Hide tab bar

## Hamburger menu

## New Tab page

### Background image

- can use any image, including a GIF!
```css
@-moz-document url("about:home"), url("about:newtab") {
  body {
    background: url("wallpaper.jpg") center/cover no-repeat fixed !important;
  }
}
```
## Icons in menus


## Hide URL status bar

![image](https://user-images.githubusercontent.com/38451588/180997690-7c4be005-07bc-48b1-a91e-af21f885b6de.png)


```css
#statuspanel {display: none !important ;}
```

## Minimise, Maximise/Restore, Close window buttons

![image](https://user-images.githubusercontent.com/38451588/180999377-214f24a5-6b0f-4a6a-a08a-82d4d20e791c.png)

```css
.titlebar-button > .toolbarbutton-icon {
  background: #1154bf !important;
  list-style-image: none;
  border-radius: 10px;
}
.titlebar-min > .toolbarbutton-icon { background: #158b93 !important; }
.titlebar-close > .toolbarbutton-icon { background: #a42f54 !important; }

.titlebar-button {
  background: transparent !important;
  padding-inline: 5px !important;
}
```
