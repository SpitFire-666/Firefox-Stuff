# Firefox-Stuff

### POWERSHELL

````powershell
# Create a user.js and open it in Notepad
IF (test-path $env:USERPROFILE\appdata\roaming\mozilla\firefox\profiles){
$profilefolder = (ls $env:USERPROFILE\appdata\roaming\mozilla\firefox\profiles | sort lastwritetime -Descending | select -first 1 ).fullname
$configfile = new-item -Path $profilefolder -Name user.js -Type File
}
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

// F12 devtools - dark theme
user_pref("devtools.theme", dark);

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


#notepad $configfile
#}
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

# Add Ons / Extensions
| Essential? | Name/Link | What | Why | Custom settings |
|-|-|-|-|-|
| |Imagus | | | Set to enabled when holding Ctrl | |
|✅ | uBlock Origin | Use the EasyList Cookie list too ![image](https://user-images.githubusercontent.com/38451588/143425758-f3eaaa7c-9894-4099-824b-a329b6884a3f.png) https://gitlab.com/DandelionSprout/adfilt/-/raw/master/LegitimateURLShortener.txt | |
| (SUPERSEDED) | ClearURLs https://addons.mozilla.org/en-US/firefox/addon/clearurls/ | |
|✅ | LocalCDN | | 
| | FeedBro | RSS Reader | 
| | Tab count in window title |
| | QR code | Generates a QR code for the current page |
|✅ | Everything Metric | Converts yankee units to metric! |
| | Dark Reader |
| | SponsorBlock for YouTube | | |
| | Tree Style Tab | 
| | WebMail Ad blocker |
| | Link Status Redux | 
| | Linkificator | 
| | Reddit Enhancement Suite | 
| | Custom Top Sort for Reddit | 
| | Skip Redirect |
| | Redirector |
| ✅ | Old Reddit Redirect | https://addons.mozilla.org/en-US/firefox/addon/old-reddit-redirect/ | 
| ✅ | Don't track me Google https://addons.mozilla.org/en-US/firefox/addon/dont-track-me-google1/ | At the Google Search engine, search results are converted to an ugly link upon click. This link enables tracking for Google. This addon removes Google's link-conversion/tracking feature. This speeds up loading search results and allows you to normally copy links. | |


# Tips / Tricks

- If you start your search with ^ it will restrict suggestions to your history
- Typing % in the address bar will search open tabs
- Disable sites from hijacking the right click menu (WIP)
- Force a crash using this tool:
- If you bookmark and tag a page you want to get back to, all you have to do is type * in the address (URL bar), followed by a tag, and it'll 'suggest' the sites that share that tag. 
- How to highlight/select linked text or part of a table

# Internal pages

|a | b| c|
|-|-|-|
|about:crashes | | |
| about:cache | | |
| about:memory | | |
| about:telemetry | | 
| about:protections | |
| about:performance | |
