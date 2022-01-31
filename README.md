# Firefox

## Why Firefox?



- uBlock Origin works best on Firefox
- Ctrl + Tab MRU tab switching - including ability to Ctrl + W to close a tab in the dialog!
- Multi-Account Containers
- You can copy the text of a hyperlink by holding Alt and selecting the text. To do this in Edge, I have to Inspect Element
- Dev Tools - Firefox exposes the domain in Network tab by default - Chrome and Edge hide this by default
- Customisation - you can drop/edit a user.js file to change most settings. I can't find a good way to export/import Edge settings (except GPO)
- The only major browser that's NOT built on Google's chromium codebase (besides Safari on iOS)
- You can circumvent sites that block right-clicking by holding Ctrl + right click
- Reader view circumvents many paywalls!
- SSL/certificate/HTTPS issues can be permanently excepted/stored. On Chrome you have to choose Advanced, then Proceed every time.
- Multiple Picture-In-Picture PiP
- Simpler homepage config. Edge for example is very confusing
- Video autoplay control
- Mozilla are working on a native translation feature (with less reliance on Google)
- Firefox doesn't insert its tabs into Alt+Tab like Edge does (and you have to navigate the Windows multitasking settings to change that!)
- Firefox has an accellerator key for Inspect Element (Q). Edge and Chrome don't have this.



# Add Ons / Extensions
| Essential? | Name/Link | What | Why | Tips |
|-|-|-|-|-|
| | Imagus https://addons.mozilla.org/en-US/firefox/addon/imagus/ | Enlarge thumbnails, and show images/videos from links with a mouse hover. | | Set to enabled when holding Ctrl | |
|✅ | uBlock Origin https://addons.mozilla.org/en-US/firefox/addon/ublock-origin/ | Best ad-blocker. Use the EasyList Cookie list too ![image](https://user-images.githubusercontent.com/38451588/143425758-f3eaaa7c-9894-4099-824b-a329b6884a3f.png) https://gitlab.com/DandelionSprout/adfilt/-/raw/master/LegitimateURLShortener.txt | |
|✅ | LocalCDN https://addons.mozilla.org/en-US/firefox/addon/localcdn-fork-of-decentraleyes/ | Emulates remote frameworks (e.g. jQuery, Bootstrap, AngularJS) and delivers them as local resource. Prevents unnecessary 3rd party requests to Google, StackPath, MaxCDN and more. | Faster browsing, less reliance on having to download 3rd party (eg Google) resources |
| | FeedBro | RSS Reader | 
| | Tab count in window title |
| | QR code | Generates a QR code for the current page |
|✅ | Everything Metric https://addons.mozilla.org/en-US/firefox/addon/everything-metric-converter/ | Converts yankee units to metric! |
| | Dark Reader | 
| | SponsorBlock for YouTube https://addons.mozilla.org/en-US/firefox/addon/sponsorblock/| | |
| | Tree Style Tab | 
| | WebMail Ad blocker |
| | Link Status Redux | 
| | Linkificator | Converts text into hyperlinks | 
| | Reddit Enhancement Suite | 
| | Custom Top Sort for Reddit https://addons.mozilla.org/en-US/firefox/addon/custom-top-sort-for-reddit/ | Allow Reddit's top sort to use other time durations than the default ones. |
| | Skip Redirect | 
| | Redirector https://addons.mozilla.org/en-US/firefox/addon/redirector/ | Automatically redirects to user-defined urls on certain pages
| ✅ | Old Reddit Redirect | https://addons.mozilla.org/en-US/firefox/addon/old-reddit-redirect/ | Redirects all reddit links to the old Reddit |
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
