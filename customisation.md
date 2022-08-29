# userChrome.css and userContent.css tweaks/hacks!


## Pre-reqs




## Context Menu

## Prevent white flash when loading websites

```css
/* prevent white flash during page load */
@-moz-document url(chrome://browser/content/browser.xhtml)
{

  #main-window,
  browser[type="content-primary"],
  browser[type="content"],
  tabbrowser#content,
  #content,
  browser[type="content"] > html
  {
     background: #000000 !important;
  }

}
```

## Round(ed) tabs

![image](https://user-images.githubusercontent.com/38451588/181003821-12b9a395-9863-4a46-83b4-1fcf6f63fda6.png)

  .tab-background{
	border-radius: 400px !important;
	border: transparent !important;
  }

## Compact context menu

![image](https://user-images.githubusercontent.com/38451588/181004367-7c6e1dc9-074e-4492-9900-878ce4c7c20f.png)
![image](https://user-images.githubusercontent.com/38451588/181004442-31dedbe6-5298-49f1-9699-aeec99e245ba.png)

```css
/* context menu padding */
menupopup > menuitem,
menupopup > menu {
  padding-block: 2px !important;
  min-height: unset !important;
}
```

## Compact tab bar

```css
:root {
	/* reduce tab margin */
	--tab-block-margin: 3px 3px !important;
  }
  
  /* reduce tab height */
  .tabbrowser-tab {
	min-height: 24px !important;
  }
```

## Font (global)

## Hide tab bar

```css
#TabsToolbar { 
  visibility: collapse !important;
}
```


## Hamburger menu

## New Tab page

### Background image

- can use any image, including a GIF!
- Code goes in user**Content**.css NOT userChrome.css
- Need to restart Firefox for it to take effect
- Image file should be in the **chrome** folder

![image](https://user-images.githubusercontent.com/38451588/181012834-fe7766f8-8337-45bc-ba07-8df59c8641e4.png)


```css
@-moz-document url("about:home"), url("about:newtab") {
  body {
    background: url("wallpaper.jpg") center/cover no-repeat fixed !important;
  }
}
```


## Dark mode for HTML5 push notifications

![image](https://user-images.githubusercontent.com/38451588/181006322-7dcb02ec-6beb-41cd-8cc9-a67a7798407b.png)


```css
/* HTML5 dark mode web notifs */
@-moz-document url("chrome://global/content/alerts/alert.xhtml") {
	#alertBox {
	  border-color: rgb(48, 48, 48, .4) !important;
	  border-radius: 4px !important;
	  background-color: #101010 !important;
	  color: rgba(255, 255, 255, 0.800000011920929) !important;
	}

	#alertSourceLabel {
		color: #9400ff !important;
		
		/*proton color: rgb(5,209,241)*/
	  }

	#alertSettings {
	  -moz-context-properties: fill, fill-opacity !important;
	  padding: 3px !important;
	  margin: 0px 2px -3px 0px !important;
	  color: inherit !important;
	  border-radius: 4px !important;
	  transform: scale(0.91, 0.91) !important;
	}

	#alertSettings:hover,  #alertSettings[open] {
	  background-color: #313131 !important; 
	}

	menupopup {
		
		--panel-color: rgba(255, 255, 255, 0.800000011920929) !important;
		--panel-border-color: rgb(48, 48, 48) !important;
		--panel-background: #101010 !important;
		--menuitem-hover-background-color: #313131 !important;   
		--menuitem-disabled-hover-background-color: #1f1f1f !important;                    
		--menu-color: rgba(255, 255, 255, 0.8) !important;                                                           
		--menu-disabled-color:color-mix(in srgb, #101010 65%, rgb(255, 255, 255))!important; 
		--menu-border-color: var(--panel-separator-color,Field) !important;
	  }
	
	  #alertImage {
		border-radius: 4px !important;
  	}

  }
```

## Icons in menus

![image](https://user-images.githubusercontent.com/38451588/181000090-fc508bcf-58d5-4b66-bf7d-5321feb07373.png)

![image](https://user-images.githubusercontent.com/38451588/181000150-40a24108-4ce2-4f93-aaed-5f974fdaf035.png)


```css
.subviewbutton:not(.subviewbutton-iconic, [checked="true"], [targetURI]) > .toolbarbutton-icon {
  width: 16px;
  height: 16px;
  margin-inline-end: 8px !important;
  -moz-context-properties: fill, fill-opacity;
  fill: currentColor;
}
#appMenu-zoom-controls2 > label,
#fxa-manage-account-button > vbox > label {
  margin-inline-start: 24px !important;
}
.PanelUI-remotetabs-notabsforclient-label {
  margin-inline-start: 40px !important;
}
.widget-overflow-list .toolbarbutton-1:not(.toolbarbutton-combined) > .toolbarbutton-text {
  padding-inline-start: 8px !important;
}
#appMenu-fxa-label2::before,
#fxa-manage-account-button::after {
  content: "";
  display: -moz-box;
  border-radius: 50%;
  background: var(--avatar-image-url) no-repeat center/contain;
  -moz-context-properties: fill;
  fill: currentColor;
}
#appMenu-fxa-label2::before {
  width: 16px;
  height: 16px;
  margin-inline-end: 8px;
}
#fxa-manage-account-button::after {
  width: 32px;
  height: 32px;
}
.syncNowBtn {
  visibility: visible !important;
  -moz-box-ordinal-group: 0 !important;
  margin-inline-end: 8px;
}
#PanelUI-fxa-menu-setup-sync-button {
  list-style-image: url("chrome://browser/skin/sync.svg");
}
#PanelUI-fxa-menu-sendtab-button {
  list-style-image: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16"><path fill="context-fill" fill-opacity="context-fill-opacity" d="M12 0H4a2 2 0 00-2 2v2a1 1 0 001 1 1 1 0 001-1V2.5a.5.5 0 01.5-.5h7a.5.5 0 01.5.5v10a.5.5 0 01-.5.5h-7a.5.5 0 01-.5-.5V11a1 1 0 00-1-1 1 1 0 00-1 1v3a2 2 0 002 2h8a2 2 0 002-2V2a2 2 0 00-2-2zM9 15H7v-1h2z"/><path fill="context-fill" fill-opacity="context-fill-opacity" d="M5.146 10.146a.5.5 0 10.707.707l3-3a.5.5 0 000-.708l-3-3a.5.5 0 00-.707.707L7.293 7H.5a.5.5 0 000 1h6.793z"/></svg>');
}
.subviewbutton[data-l10n-id$="-settings"] {
  list-style-image: url("chrome://global/skin/icons/settings.svg");
}
#PanelUI-fxa-menu-account-signout-button {
  list-style-image: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" width="13" height="14"><path fill="context-fill" fill-opacity="context-fill-opacity" d="M6 11.375a.875.875 0 110 1.75H3.375A2.625 2.625 0 01.75 10.5v-7A2.625 2.625 0 013.375.875H6a.875.875 0 110 1.75H3.375A.875.875 0 002.5 3.5v7c0 .483.392.875.875.875zm5.871-4.996a.875.875 0 010 1.242l-2.625 2.625a.875.875 0 01-1.242 0 .875.875 0 010-1.242L9.14 7.875H5.125a.875.875 0 110-1.75h4.016L8.004 4.996a.879.879 0 011.242-1.242z"/></svg>');
}
#appMenu-new-tab-button2 {
  list-style-image: url("chrome://browser/skin/new-tab.svg");
}
#appMenu-new-window-button2,
#appMenuRecentlyClosedWindows {
  list-style-image: url("chrome://browser/skin/window.svg");
}
#appMenu-new-private-window-button2 {
  list-style-image: url("chrome://browser/skin/privateBrowsing.svg");
}
.subviewbutton[data-l10n-id="library-bookmarks-menu"],
#panelMenuBookmarkThisPage[starred],
#sidebar-switcher-bookmarks {
  list-style-image: url("chrome://browser/skin/bookmark.svg");
}
#panelMenuBookmarkThisPage {
  list-style-image: url("chrome://browser/skin/bookmark-hollow.svg");
}
#panelMenu_searchBookmarks,
#appMenu-find-button2,
#allTabsMenu-searchTabs {
  list-style-image: url("chrome://global/skin/icons/search-glass.svg");
}
#panelMenu_viewBookmarksToolbar {
  list-style-image: url("chrome://browser/skin/bookmarks-toolbar.svg");
}
.subviewbutton[id$="-history-button"],
#sidebar-switcher-history {
  list-style-image: url("chrome://browser/skin/history.svg");
}
#appMenuRecentlyClosedTabs {
  list-style-image: url("chrome://devtools/skin/images/debugging-tabs.svg");
}
#appMenuRestoreSession {
  list-style-image: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="context-fill" fill-opacity="context-fill-opacity"><path d="M13 0H3a3 3 0 00-3 3v8a3 3 0 003 3h4l-.3.4a1 1 0 101.6 1.2l1.5-2a1 1 0 000-1.2l-1.5-2a1 1 0 00-1.6 1.2l.3.4H3a1 1 0 01-1-1V5h12v6a1 1 0 01-1 1 1 1 0 000 2 3 3 0 003-3V3a3 3 0 00-3-3zM2 4V3a1 1 0 011-1h10a1 1 0 011 1v1z"/></svg>');
}
#appMenuClearRecentHistory {
  list-style-image: url("chrome://browser/skin/forget.svg");
}
.subviewbutton[id$="-downloads-button"] {
  list-style-image: url("chrome://browser/skin/downloads/downloads.svg");
}
#appMenu-passwords-button {
  list-style-image: url("chrome://browser/skin/login.svg");
}
#appMenu-extensions-themes-button {
  list-style-image: url("chrome://mozapps/skin/extensions/extension.svg");
}
#appMenu-print-button2 {
  list-style-image: url("chrome://global/skin/icons/print.svg");
}
#appMenu-save-file-button2 {
  list-style-image: url("chrome://browser/skin/save.svg");
}
.subviewbutton[command="cmd_CustomizeToolbars"] {
  list-style-image: url("chrome://browser/skin/customize.svg");
}
.subviewbutton[oncommand="switchToTabHavingURI('about:performance', true)"] {
  list-style-image: url("chrome://global/skin/icons/performance.svg");
}
.subviewbutton[key="key_browserToolbox"] {
  list-style-image: url("chrome://devtools/skin/images/fox-smiling.svg");
}
.subviewbutton[key="key_responsiveDesignMode"]:not([checked="true"]) {
  list-style-image: url("chrome://devtools/skin/images/command-responsivemode.svg");
  fill-opacity: 0;
}
.subviewbutton[key="key_responsiveDesignMode"] + .subviewbutton {
  list-style-image: url("chrome://devtools/skin/images/command-eyedropper.svg");
}
.subviewbutton[data-l10n-id="appmenu-developer-tools-extensions"] {
  list-style-image: url("chrome://activity-stream/content/data/content/assets/glyph-webextension-16.svg");
}
#appMenu-help-button2 {
  list-style-image: url("chrome://global/skin/icons/help.svg");
}
#appMenu_menu_HelpPopup_reportPhishingtoolmenu {
  list-style-image: url("chrome://global/skin/icons/lightbulb.svg");
}
#appMenu_aboutName {
  list-style-image: url("chrome://devtools/skin/images/browsers/firefox.svg");
}
#appMenu-quit-button2 {
  list-style-image: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16"><path fill="context-fill" fill-opacity="context-fill-opacity" d="M8 6a1 1 0 001-1V1a1 1 0 00-2 0v4a1 1 0 001 1zm3.5-4.032a1 1 0 00-1 1.732A4.946 4.946 0 0113 8 5 5 0 013 8a4.946 4.946 0 012.5-4.3 1 1 0 00-1-1.732 7 7 0 107.006 0z"/></svg>');
}
#allTabsMenu-containerTabsButton {
  list-style-image: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="context-fill"><rect width="6" height="6" x="1" y="1" rx="1"/><path d="M14.75 3H13V1.25a.25.25 0 00-.25-.25h-1.5a.25.25 0 00-.25.25V3H9.25a.25.25 0 00-.25.25v1.5a.25.25 0 00.25.25H11v1.75a.25.25 0 00.25.25h1.5a.25.25 0 00.25-.25V5h1.75a.25.25 0 00.25-.25v-1.5a.25.25 0 00-.25-.25z"/><rect width="6" height="6" x="1" y="9" rx="1"/><rect width="6" height="6" x="9" y="9" rx="1"/></svg>');
}
#sidebar-switcher-tabs {
  list-style-image: url("chrome://browser/skin/tab.svg");
}
#sidebar-reverse-position[label="Move Sidebar to Right"] {
  list-style-image: url("chrome://browser/skin/sidebars-right.svg");
}
#sidebar-reverse-position[label="Move Sidebar to Left"] {
  list-style-image: url("chrome://browser/skin/sidebars.svg");
}
.subviewbutton[data-l10n-id="sidebar-menu-close"] {
  list-style-image: url("chrome://global/skin/icons/close.svg");
}

menupopup:not(.in-menulist) > menu:not(.menu-iconic),
menupopup:not(.in-menulist, [aria-label]) > menuitem:not(.menuitem-iconic, [checked="true"]) {
  padding-inline-start: calc(1em + 24px) !important;
  background-position: left 1em center;
  background-repeat: no-repeat;
  background-size: 16px;
  -moz-context-properties: fill, fill-opacity;
  fill: currentColor;
}
#BMB_bookmarksPopup menuitem:not(.menuitem-iconic),
#PlacesToolbar .openintabs-menuitem {
  padding-inline-start: 32px !important;
  background-position-x: 8px;
}
#menu_newNavigatorTab,
menuitem[id$="openANewTab"] {
  background-image: url("chrome://browser/skin/new-tab.svg");
}
#menu_newUserContext {
  background-image: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="context-fill"><rect width="6" height="6" x="1" y="1" rx="1"/><path d="M14.75 3H13V1.25a.25.25 0 00-.25-.25h-1.5a.25.25 0 00-.25.25V3H9.25a.25.25 0 00-.25.25v1.5a.25.25 0 00.25.25H11v1.75a.25.25 0 00.25.25h1.5a.25.25 0 00.25-.25V5h1.75a.25.25 0 00.25-.25v-1.5a.25.25 0 00-.25-.25z"/><rect width="6" height="6" x="1" y="9" rx="1"/><rect width="6" height="6" x="9" y="9" rx="1"/></svg>');
}
#menu_newNavigator,
#historyUndoWindowMenu,
menuitem[data-l10n-id*="-open-"][data-l10n-id$="-window"] {
  background-image: url("chrome://browser/skin/window.svg");
}
menuitem[data-l10n-id$="-private-window"] {
  background-image: url("chrome://browser/skin/privateBrowsing.svg") !important;
}
#menu_openFile {
  background-image: url("chrome://browser/skin/open.svg");
}
#menu_savePage,
#context-savepage {
  background-image: url("chrome://browser/skin/save.svg");
}
menuitem[data-l10n-id*="-email"] {
  background-image: url("chrome://browser/skin/mail.svg");
}
menuitem[data-l10n-id*="-print"] {
  background-image: url("chrome://global/skin/icons/print.svg");
}
#menu_importFromAnotherBrowser,
#browserImport {
  background-image: url("chrome://browser/skin/import.svg");
}
#menu_FileQuitItem {
  background-image: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16"><path fill="context-fill" fill-opacity="context-fill-opacity" d="M8 6a1 1 0 001-1V1a1 1 0 00-2 0v4a1 1 0 001 1zm3.5-4.032a1 1 0 00-1 1.732A4.946 4.946 0 0113 8 5 5 0 013 8a4.946 4.946 0 012.5-4.3 1 1 0 00-1-1.732 7 7 0 107.006 0z"/></svg>');
}
menuitem[data-l10n-id="text-action-undo"],
menuitem[data-l10n-id$="-reopen-closed-tabs"] {
  background-image: url("chrome://global/skin/icons/undo.svg");
}
menuitem[data-l10n-id="text-action-cut"] {
  background-image: url("chrome://browser/skin/edit-cut.svg");
}
menuitem[data-l10n-id="text-action-copy"],
#syncedTabsCopySelected {
  background-image: url("chrome://global/skin/icons/edit-copy.svg");
}
menuitem[data-l10n-id="text-action-paste"] {
  background-image: url("chrome://browser/skin/edit-paste.svg");
}
menuitem[data-l10n-id="text-action-delete"],
.customize-context-removeExtension,
menuitem[data-l10n-id="toolbar-context-menu-remove-from-toolbar"],
.downloadRemoveFromHistoryMenuItem,
menuitem[id^="placesContext_delete"] {
  background-image: url("chrome://global/skin/icons/delete.svg");
}
#menu_find,
#context-searchselect {
  background-image: url("chrome://global/skin/icons/search-glass.svg");
}
#toggle_PersonalToolbar,
#BMB_viewBookmarksToolbar {
  background-image: url("chrome://browser/skin/bookmarks-toolbar.svg");
}
menuitem[data-l10n-id*="-customize-toolbar"] {
  background-image: url("chrome://browser/skin/customize.svg");
}
#viewSidebarMenuMenu,
#BMB_viewBookmarksSidebar {
  background-image: url("chrome://browser/skin/sidebars.svg");
}
#menu_bookmarksSidebar:not([checked="true"]),
menuitem[data-l10n-id="menu-bookmark-edit"] {
  background-image: url("chrome://browser/skin/bookmark.svg") !important;
}
#menu_historySidebar:not([checked="true"]) {
  background-image: url("chrome://browser/skin/history.svg");
}
#menu_tabsSidebar:not([checked="true"]),
#sync-tabs-menuitem {
  background-image: url("chrome://browser/skin/tab.svg");
}
#menu_zoomEnlarge {
  background-image: url("chrome://browser/skin/add-circle-fill.svg");
}
#menu_zoomReduce {
  background-image: url("chrome://browser/skin/subtract-circle-fill.svg");
}
#repair-text-encoding {
  background-image: url("chrome://browser/skin/characterEncoding.svg");
}
#fullScreenItem:not([checked="true"]) {
  background-image: url("chrome://browser/skin/fullscreen.svg");
}
#menu_readerModeItem {
  background-image: url("chrome://browser/skin/reader-mode.svg");
}
#sanitizeItem,
#placesContext_deleteHost {
  background-image: url("chrome://browser/skin/forget.svg");
}
#historyRestoreLastSession {
  background-image: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="context-fill" fill-opacity="context-fill-opacity"><path d="M13 0H3a3 3 0 00-3 3v8a3 3 0 003 3h4l-.3.4a1 1 0 101.6 1.2l1.5-2a1 1 0 000-1.2l-1.5-2a1 1 0 00-1.6 1.2l.3.4H3a1 1 0 01-1-1V5h12v6a1 1 0 01-1 1 1 1 0 000 2 3 3 0 003-3V3a3 3 0 00-3-3zM2 4V3a1 1 0 011-1h10a1 1 0 011 1v1z"/></svg>');
}
#historyUndoMenu {
  background-image: url("chrome://devtools/skin/images/debugging-tabs.svg");
}
menuitem[data-l10n-id*="bookmark-"]:not(.menuitem-iconic),
#context-bookmarkframe,
#placesContext_createBookmark {
  background-image: url("chrome://browser/skin/bookmark-hollow.svg");
}
#menu_openDownloads {
  background-image: url("chrome://browser/skin/downloads/downloads.svg");
}
#menu_openAddons {
  background-image: url("chrome://mozapps/skin/extensions/extension.svg");
}
#sync-setup {
  background-image: var(--avatar-image-url);
}
menuitem[data-l10n-id$="-sync-now"] {
  background-image: url("chrome://browser/skin/sync.svg");
}
#webDeveloperMenu {
  background-image: url("chrome://browser/skin/developer.svg");
}
#menu_taskManager {
  background-image: url("chrome://global/skin/icons/performance.svg");
}
#menu_browserToolbox {
  background-image: url("chrome://devtools/skin/images/fox-smiling.svg");
}
#menu_responsiveUI:not([checked="true"]) {
  background-image: url("chrome://devtools/skin/images/command-responsivemode.svg");
  fill-opacity: 0;
}
#menu_eyedropper {
  background-image: url("chrome://devtools/skin/images/command-eyedropper.svg");
}
#extensionsForDevelopers {
  background-image: url("chrome://activity-stream/content/data/content/assets/glyph-webextension-16.svg");
}
#menu_pageInfo,
#context-viewframeinfo {
  background-image: url("chrome://global/skin/icons/info.svg");
}
#menu_preferences,
#openSettingsMenuItem {
  background-image: url("chrome://global/skin/icons/settings.svg");
}
#menu_HelpPopup_reportPhishingtoolmenu {
  background-image: url("chrome://global/skin/icons/lightbulb.svg");
}
#aboutName {
  background-image: url("chrome://devtools/skin/images/browsers/firefox.svg");
}
menuitem[data-l10n-id*="reload-"],
#context-reloadframe {
  background-image: url("chrome://global/skin/icons/reload.svg");
}
menuitem[id^="context_toggleMute"]:not([soundplaying], [muted]),
menuitem[id^="context_toggleMute"][soundplaying]:not([muted]),
#context-media-mute {
  background-image: url("chrome://global/skin/media/audio-muted.svg");
}
menuitem[id^="context_toggleMute"][muted],
#context-media-unmute {
  background-image: url("chrome://global/skin/media/audio.svg");
}
menuitem[data-l10n-id^="pin-"],
.customize-context-moveToPanel {
  background-image: url("chrome://activity-stream/content/data/content/assets/glyph-pin-16.svg");
}
menuitem[data-l10n-id^="unpin-"],
.customize-context-moveToToolbar {
  background-image: url("chrome://activity-stream/content/data/content/assets/glyph-unpin-16.svg");
}
menuitem[id^="context_duplicateTab"] {
  background-image: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="context-fill" fill-opacity="context-fill-opacity"><path d="M15 13a1 1 0 000-2h-1V5a2 2 0 00-2-2H8.402a2 2 0 00-2 2v6h-1a1 1 0 000 2"/><path d="M5.281 10V5c0-.771.301-1.468.78-2H4a2 2 0 00-2 2v6H1a1 1 0 000 2h2.559a1.978 1.978 0 01-.278-1c0-1.103.897-2 2-2z"/></svg>');
}
#context_moveTabOptions {
  background-image: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="context-fill" fill-opacity="context-fill-opacity"><path d="M15.854 12.14s-.001 0 0 0l-3.001-3.001a.496.496 0 00-.707.013.5.5 0 000 .695l2.147 2.148H7.5a.5.5 0 000 1h6.793l-2.147 2.146a.5.5 0 10.695.719l.012-.012 3-3a.5.5 0 00.001-.708z"/><path d="M7.5 10.994h4.38l-.453-.453a1.495 1.495 0 010-2.084 1.503 1.503 0 012.133-.025l.44.44V5a2 2 0 00-2-2H4a2 2 0 00-2 2v6H1a1 1 0 000 2h5.094A1.49 1.49 0 016 12.494c0-.827.673-1.5 1.5-1.5z"/></svg>');
}
menu.sync-ui-item {
  background-image: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16"><path fill="context-fill" fill-opacity="context-fill-opacity" d="M12 0H4a2 2 0 00-2 2v2a1 1 0 001 1 1 1 0 001-1V2.5a.5.5 0 01.5-.5h7a.5.5 0 01.5.5v10a.5.5 0 01-.5.5h-7a.5.5 0 01-.5-.5V11a1 1 0 00-1-1 1 1 0 00-1 1v3a2 2 0 002 2h8a2 2 0 002-2V2a2 2 0 00-2-2zM9 15H7v-1h2z"/><path fill="context-fill" fill-opacity="context-fill-opacity" d="M5.146 10.146a.5.5 0 10.707.707l3-3a.5.5 0 000-.708l-3-3a.5.5 0 00-.707.707L7.293 7H.5a.5.5 0 000 1h6.793z"/></svg>');
}
menuitem.sendtab-target[clientType="desktop"] {
  background-image: url("chrome://browser/skin/device-desktop.svg");
}
menuitem.sendtab-target[clientType="phone"] {
  background-image: url("chrome://browser/skin/device-phone.svg");
}
menuitem.sendtab-target[clientType="tablet"] {
  background-image: url("chrome://browser/skin/device-tablet.svg");
}
menuitem.sendtab-target[clientType="tv"] {
  background-image: url("chrome://browser/skin/device-tv.svg");
}
menuitem.sendtab-target[clientType="vr"] {
  background-image: url("chrome://browser/skin/device-vr.svg");
}
.share-tab-url-item {
  background-image: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16"><path fill="context-fill" d="M12.707 4.294l-4-4A1 1 0 008.38.077a.984.984 0 00-.246-.05A.938.938 0 008 0a.938.938 0 00-.134.027.984.984 0 00-.246.05A1 1 0 007.291.3l-4 4a1 1 0 001.416 1.408L7 3.415V11a1 1 0 002 0V3.415l2.293 2.293a1 1 0 001.414-1.414z"/><path fill="context-fill" d="M14 9a1 1 0 00-1 1v3a1 1 0 01-1 1H4a1 1 0 01-1-1v-3a1 1 0 00-2 0v3a3 3 0 003 3h8a3 3 0 003-3v-3a1 1 0 00-1-1z"/></svg>');
}
#context_reopenInContainer,
#context-openlinkinusercontext-menu {
  background-image: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="context-fill"><rect width="6" height="6" x="1" y="1" rx="1"/><rect width="6" height="6" x="1" y="9" rx="1"/><rect width="6" height="6" x="9" y="9" rx="1"/><path d="M14.92 1.62a1 1 0 00-.54-.54A1 1 0 0014 1h-4a1 1 0 000 2h1.59l-2.3 2.29a1 1 0 000 1.42 1 1 0 001.42 0L13 4.41V6a1 1 0 002 0V2a1 1 0 00-.08-.38z"/></svg>');
}
#context_closeTab,
#orgClose {
  background-image: url("chrome://global/skin/icons/close.svg");
}
#context_closeTabOptions {
  background-image: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16"><path fill="context-fill" fill-opacity="context-fill-opacity" d="M14.3 10l-1.8 1.8-1.8-1.8c-.2-.2-.5-.2-.7 0s-.2.5 0 .7l1.8 1.8-1.8 1.8c-.2.2-.2.5 0 .7s.5.2.7 0l1.8-1.8 1.8 1.8c.2.2.5.2.7 0s.2-.5 0-.7l-1.8-1.8 1.8-1.8c.2-.2.2-.5 0-.7s-.5-.2-.7 0z"/><path fill="context-fill" fill-opacity="context-fill-opacity" d="M16 12c0-.2-.1-.5-.2-.6l-1.1 1.1.5.5c.4-.1.8-.5.8-1zm-5.6.5L9 11.1c-.4-.4-.4-1 0-1.4l.7-.7c.4-.4 1-.4 1.4 0l1.4 1.4L13.9 9s.1 0 .1-.1V5c0-1.1-.9-2-2-2H4c-1.1 0-2 .9-2 2v6H1c-.6 0-1 .4-1 1s.4 1 1 1h8.9l.5-.5z"/></svg>');
}
menuitem[data-l10n-id="full-screen-exit"] {
  background-image: url("chrome://browser/skin/fullscreen-exit.svg");
}
#paste-and-go {
  background-image: url("chrome://browser/skin/forward.svg");
}
.customize-context-reportExtension {
  background-image: url("chrome://global/skin/icons/warning.svg");
}
.downloadShowMenuItem {
  background-image: url("chrome://global/skin/icons/folder.svg");
}
menuitem[id^="context-open"]:is([id$="intab"], [id$="incontainertab"]),
menuitem[data-l10n-id$="-view-new-tab"],
menuitem[data-l10n-id*="-open-in-"][data-l10n-id$="-tab"] {
  background-image: url("chrome://global/skin/icons/open-in-new.svg");
}
menuitem[oncommand^="Pocket.savePage"] {
  background-image: url("chrome://browser/skin/pocket-outline.svg");
}
menuitem[data-l10n-id$="-screenshot"] {
  background-image: url("chrome://browser/skin/screenshot.svg");
}
menuitem[data-l10n-id*="-copy-"][data-l10n-id*="-link"] {
  background-image: url("chrome://global/skin/icons/link.svg");
}
#context-searchselect[label^="Search Google for "] {
  background-image: url("chrome://activity-stream/content/data/content/tippytop/favicons/google-com.ico");
}
#context-searchselect[label^="Search Bing for "] {
  background-image: url("chrome://activity-stream/content/data/content/tippytop/favicons/bing-com.ico");
}
#context-searchselect[label^="Search DuckDuckGo for "] {
  background-image: url("chrome://activity-stream/content/data/content/tippytop/favicons/duckduckgo-com.ico");
}
#context-inspect-a11y {
  background-image: url("chrome://devtools/skin/images/tool-accessibility.svg");
}
#context-inspect {
  background-image: url("chrome://devtools/content/shared/images/command-pick.svg");
}
#context-media-play {
  background-image: url("chrome://global/skin/media/play-fill.svg");
}
#context-media-pause,
#doNotDisturbMenuItem {
  background-image: url("chrome://global/skin/media/pause-fill.svg");
}
#context-video-fullscreen {
  background-image: url("chrome://global/skin/media/fullscreenEnterButton.svg");
}
#context-leave-dom-fullscreen {
  background-image: url("chrome://global/skin/media/fullscreenExitButton.svg");
}
#context-video-pictureinpicture:not([checked="true"]) {
  background-image: url("chrome://global/skin/media/picture-in-picture-open.svg");
}
#context-video-saveimage {
  background-image: url("chrome://devtools/skin/images/command-screenshot.svg");
}
#disableForOriginMenuItem {
  background-image: url("chrome://browser/skin/notification-icons/desktop-notification-blocked.svg");
}
menuitem[data-l10n-id^="places-edit-"] {
  background-image: url("chrome://global/skin/icons/edit.svg");
}
```

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
