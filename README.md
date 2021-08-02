# Firefox-Settings

````powershell
# Create a user.js and open it in Notepad
IF (test-path $env:USERPROFILE\appdata\roaming\mozilla\firefox\profiles){
$profilefolder = (ls $env:USERPROFILE\appdata\roaming\mozilla\firefox\profiles | sort lastwritetime -Descending | select -first 1 ).fullname
$configfile = new-item -Path $profilefolder -Name user.js -Type File
notepad $configfile
}
````


````javascript
// Ctrl + Tab MRU
user_pref("browser.ctrlTab.sortByRecentlyUsed",true);

// Disable Pocket extension
user_pref("extensions.pocket.enabled", false);

// Submit crash reports
user_pref("browser.crashReports.unsubmittedCheck.autoSubmit2", true);

// F12 tools - Set Network tab first
user_pref("devtools.toolbox.selectedTool", netmonitor);
user_pref("devtools.toolbox.tabsOrder", netmonitor,inspector,webconsole,jsdebugger,styleeditor,performance,memory,storage,accessibility,application);

// Dark Theme
user_pref("extensions.activeThemeID", firefox-compact-dark@mozilla.org);

user_pref("extensions.pictureinpicture.enable_picture_in_picture_overrides", true);

// Disable Web Search Suggestions
user_pref("browser.search.suggest.enabled", false);
user_pref("browser.search.suggest.enabled.private", false);
// Search region
user_pref("browser.search.region", AU);


// Stop sites preventing access to right click menu
user_pref("dom.event.contextmenu.enabled", false);


// set DDG as search engine


// dark mode for dev tools (f12)

// add zoom to toolbar

// override courier new font to something nicer

// restore previous session

// Use OS settings for dates etc

// allow firefox to send backlogged crash reports

// allow addons to run on protected/internal pages

````

Restart Firefox

Add Ons


