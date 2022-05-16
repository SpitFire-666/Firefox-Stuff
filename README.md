# Firefox Stuff

A fan page. Info, tips, add-ons and more. 

Tips/suggestions welcome!

## Why use Firefox? Features/functionality that's unique to Firefox

After being forced to use Edge/Chrome at work, I've found many things Firefox does better:

- **uBlock Origin** works best on Firefox: 
- **Ctrl + Tab MRU tab switcher** - including ability to Ctrl + W to close a tab in the dialog!

![image](https://user-images.githubusercontent.com/38451588/168515810-84a75560-62ac-441e-be99-b539fe0966c2.png)

- **Multi-Account Containers!** Edge and Chrome have addons for this but they suck
- In Firefox, you can copy the text of a hyperlink by holding Alt and selecting the text. To do this in Edge, you have to Inspect Element
- Dev Tools - Firefox exposes the domain in Network tab by default - Chrome and Edge hide this by default
- Customisation - you can drop/edit a user.js file to change most settings. I can't find a good way to export/import Edge settings (except GPO)
- The only major browser that's NOT built on Google's chromium codebase (besides Safari on iOS/OSX)
- You can circumvent sites that block right-clicking by holding Ctrl + right click
- SSL/certificate/HTTPS issues can be permanently excepted/stored. On Chrome you have to choose Advanced, then Proceed each time.

- Simple homepage config. Edge for example is very confusing
- **Video autoplay control**: 
- Mozilla are working on a native translation feature (with less reliance on Google)
- Firefox doesn't clutter Alt+Tab with its tabs like Edge does (and you have to navigate the Windows multitasking settings to change that!)
- Firefox has an . Edge and Chrome don't have this.
- Firefox shows the URL of a link on hover - Edge obscures it (you have to hover for a couple seconds for it to show you the complete URL). Chrome at least shows it immediately like Firefox
- In dev tools, you can select multiple categories, eg Font and Img. Chrome/Edge allow only you to choose only one category at a time

![image](https://user-images.githubusercontent.com/38451588/168515713-dd3662b4-d606-495e-a270-98c638135b71.png)

- **Developer Tools** can be popped out into a window. Chrome and Edge do not allow this

![image](https://user-images.githubusercontent.com/38451588/166852122-62e6d2df-0d77-4b84-abab-cadf3cedadef.png)


| Feature | Firefox | Chrome | Edge | Comment |
|-|-|-|-|-|
| Subtitles in Picture-in-Picture | ✅ | | |
| Multi Account Containers | ✅| ⛔| ⛔| While some hacks/workarounds exist, none work as well as Firefox's| 
| Ctrl+Tab MRU tab switcher | ✅ |||
| Reader View | ✅ | ⛔ |⛔| Reader View is a Firefox feature that strips away clutter like buttons, ads, background images, and videos while also letting you customize the layout and theme to fit your reading preferences. It can sometimes bypass paywalls! |
| Multiple Picture-in-Picture | ✅ | | | |
| Video autoplay control | ✅ | | | Blocks many videos from auto-playing by default |
| uBlock Origin: best experience | ✅ | ⛔| ⛔| https://github.com/gorhill/uBlock/wiki/uBlock-Origin-works-best-on-Firefox |
| Ability to disable search engine suggestions | ✅ | | ⛔| Sorry, I don't want my browser trying to read my mind, and I don't want my keystrokes to be harvested either! |
| Open dev tools immediately using F12 | ✅ | | | Edge asks for confirmation first! |
| Vertical tabs/Tree Style Tabs | ✅ | ⛔ | ✅ | Edge has this built-in, but without any heirachy like Tree Style Tabs. Half a point to Edge! | 
| Enhanced Tracking Protection | | | |
| Developer Tools: pop out into a separate window | ✅ |⛔ | ⛔| |
| Developer Tools: show Network tab by default | ✅ | ⛔|⛔| What are the big boys trying to hide?? |
| Accelerator key for Inspect Element (Q) | ✅ | ⛔ | ⛔ | Minor, but why not have it? |

# Recommended Add-Ons / Extensions

| Essential? | Name/Link | What | Why | Tips |
|-|-|-|-|-|
| | [Imagus](https://addons.mozilla.org/en-US/firefox/addon/imagus/) | Enlarge thumbnails, and show images/videos from links with a mouse hover. | | Set to enabled when holding Ctrl | |
|✅ | [uBlock Origin](https://addons.mozilla.org/en-US/firefox/addon/ublock-origin/) | Best ad-blocker. Enable the EasyList Cookie list too ![image](https://user-images.githubusercontent.com/38451588/143425758-f3eaaa7c-9894-4099-824b-a329b6884a3f.png) Also add the Legitimate URL Shortener list:  https://gitlab.com/DandelionSprout/adfilt/-/raw/master/LegitimateURLShortener.txt | |
|✅ | [LocalCDN](https://addons.mozilla.org/en-US/firefox/addon/localcdn-fork-of-decentraleyes/) | Emulates remote frameworks (e.g. jQuery, Bootstrap, AngularJS) and delivers them as local resource. Prevents unnecessary 3rd party requests to Google, StackPath, MaxCDN and more. | Faster browsing, less reliance on having to download 3rd party (eg Google) resources |
| | FeedBro | RSS Reader | |
| | [Tab Count Icon](https://addons.mozilla.org/en-US/firefox/addon/tab-count-icon/) | Shows number of open tabs on the toolbar |
| | [QR](https://addons.mozilla.org/en-US/firefox/addon/qr/) | Generates a QR code for the current page |
|✅ | [Everything Metric](https://addons.mozilla.org/en-US/firefox/addon/everything-metric-converter/) | Converts yankee/imperial units to metric! |
| | [Dark Reader](https://addons.mozilla.org/en-US/firefox/addon/darkreader/) | 
| | [SponsorBlock for YouTube](https://addons.mozilla.org/en-US/firefox/addon/sponsorblock/)| Easily skip YouTube video sponsors. When you visit a YouTube video, the extension will check the database for reported sponsors and automatically skip known sponsors. You can also report sponsors in videos. | |
| | [Tree Style Tab](https://addons.mozilla.org/en-US/firefox/addon/tree-style-tab/) | 
| | [WebMail Ad blocker](https://addons.mozilla.org/en-US/firefox/addon/webmail-ad-blocker/) | Remove advertising clutter from your web-based email. Expand your viewable area by blocking and removing ads on the right-hand side of the screen when using Gmail, Hotmail, Outlook.com and Yahoo Mail.
| | [Link Status Redux](https://addons.mozilla.org/en-US/firefox/addon/link-status-redux/) | Shows an indicator on a popup panel next to the link address when the mouse cursor is over a link to a page you have bookmarked or visited before, or if the link is currently open in a browser tab. |
| | Linkificator | Converts text links into clickable hyperlinks | 
| | [Reddit Enhancement Suite](https://addons.mozilla.org/en-US/firefox/addon/reddit-enhancement-suite) | |
| | [Custom Top Sort for Reddit](https://addons.mozilla.org/en-US/firefox/addon/custom-top-sort-for-reddit/) | Allow Reddit's top sort to use other time durations than the default ones. |
| | [Redirector](https://addons.mozilla.org/en-US/firefox/addon/redirector/) | Automatically redirects to user-defined urls on certain pages
| ✅ | [Old Reddit Redirect](https://addons.mozilla.org/en-US/firefox/addon/old-reddit-redirect/) | Redirects all reddit links to the old Reddit |
| ✅ | [Don't track me Google](https://addons.mozilla.org/en-US/firefox/addon/dont-track-me-google1/) | Google Search results are converted to an ugly link upon click. This link enables tracking for Google. This addon removes Google's link-conversion/tracking feature. This speeds up loading search results and allows you to normally copy links. | |
| ✅ | [Bypass Twitter login](https://addons.mozilla.org/en-US/firefox/addon/twitter-without-logging-in/) | Get around Twitter's login modal and still scroll tweets. This extension will add a button to your toolbar. When Twitter throws up a login wall, press the button and you'll be able to continue browsing. |
| | [LibRedirect](https://addons.mozilla.org/en-US/firefox/addon/libredirect/) | Redirects Twitter, YouTube, Instagram and more to privacy friendly alternatives. | |


# userChrome.css

Use this if you want to customise Firefox, eg by hiding the tab strip

- Enable in about:config by setting ``toolkit.legacyUserProfileCustomizations.stylesheets`` to ``true``
- Open your Firefox profile folder (go to about:support > Profile Folder > Open Folder
- Create new folder "chrome" in your profile
- Create new file userChrome.css in your profile's chrome folder
- Edit the userChrome.css file with tweaks
- Restart Firefox

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

# user.js

Use this file to modify preferences outside of the browser

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
