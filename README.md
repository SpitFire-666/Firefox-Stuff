# Firefox-Settings

### POWERSHELL

````powershell
# Create a user.js and open it in Notepad
IF (test-path $env:USERPROFILE\appdata\roaming\mozilla\firefox\profiles){
$profilefolder = (ls $env:USERPROFILE\appdata\roaming\mozilla\firefox\profiles | sort lastwritetime -Descending | select -first 1 ).fullname
$configfile = new-item -Path $profilefolder -Name user.js -Type File

############# FIREFOX CONFIG ###############

$settings = @"
// Dark Theme
user_pref("browser.theme.toolbar-theme", 0);

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
// Not possible via user.js....

// dark mode for dev tools (f12)
user_pref("devtools.theme", dark);

// add zoom to toolbar

// override courier new font to something nicer
user_pref("font.name.monospace.x-western", Consolas);

// restore previous session

// Use OS settings for dates etc
user_pref("intl.regional_prefs.use_os_locales", true);


// allow firefox to send backlogged crash reports

// *** TBD: allow addons to run on protected/internal pages
// extensions.webextensions.restrictedDomains

// Disable accessibility services (faster)
user_pref("accessibility.force_disabled", true); 

// Enable SSO for Microsoft services
user_pref("network.http.windows-sso.enabled", true); 

// Disable sponsored content on New Tabs

user_pref("browser.newtabpage.activity-stream.showSponsored", false);
user_pref("browser.newtabpage.activity-stream.showSponsoredTopSites", false);


// Allow all addons to run in private mode
"@

$settings | out-file $configfile


notepad $configfile
}
````


````javascript
// Dark Theme
user_pref("browser.theme.toolbar-theme", 0);

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
// Not possible via user.js....

// dark mode for dev tools (f12)
user_pref("devtools.theme", dark);

// add zoom to toolbar

// override courier new font to something nicer
user_pref("font.name.monospace.x-western", Consolas);

// restore previous session

// Use OS settings for dates etc
user_pref("intl.regional_prefs.use_os_locales", true);


// allow firefox to send backlogged crash reports

// *** TBD: allow addons to run on protected/internal pages
// extensions.webextensions.restrictedDomains

// Disable accessibility services (faster)
user_pref("accessibility.force_disabled", true); 

// Enable SSO for Microsoft services
user_pref("network.http.windows-sso.enabled", true); 


// Allow all addons to run in private mode
````

Restart Firefox

Add Ons


