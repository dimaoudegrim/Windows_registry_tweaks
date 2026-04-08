----🚀 Performance & Memory----
*	MaxCachedIcons = 4096 — Increases the icon cache size so Windows stores more icons, reducing reloading lag
*	WaitForIdleState = 0 (both HKLM & HKCU) — Removes the idle-wait requirement before Explorer starts loading, speeding up startup
*	StartupDelayInMSec = 0 (both HKLM & HKCU) — Eliminates the artificial startup delay Explorer adds on boot
*	DisablePagingExecutive = 1 — Forces kernel and drivers to stay in RAM instead of being paged to disk, improving responsiveness
*	Win32PrioritySeparation = 0x16 — Tunes CPU time slicing to favor foreground apps (balanced short intervals)
*	SystemResponsiveness = 10 — Allows multimedia/games to use up to 90% of CPU, reserving only 10% for background tasks
*	NetworkThrottlingIndex = 0xFFFFFFFF — Disables network throttling for multimedia streams, maximizing throughput
*	LargeSystemCache = 0 — Keeps the system cache optimized for desktop/application use rather than server-style file caching
*	EnableSuperfetch = 0 — Disables Superfetch (SysMain) preloading, reducing background disk activity
*	EnablePrefetcher = 0 — Disables Prefetcher, stopping Windows from preloading application data into RAM
*	ServicesPipeTimeout = 0x7530 (30 seconds) — Increases the timeout before Windows gives up waiting for a service to respond on startup/shutdown
  
----🎮 Gaming Priority----
*	Games Priority = 6 — Sets the CPU scheduling priority for game processes to high
*	Games Scheduling Category = High — Puts games in the high scheduling bucket so they get preferential CPU time
*	Games SFIO Priority = High — Gives game processes high-priority storage I/O access
  
----🔇 Search & Cortana----
*	DisableSearchBoxSuggestions = 1 — Removes autocomplete suggestions from the Start menu search box
*	AllowCortana = 0 — Disables Cortana entirely via policy
*	DisableWebSearch = 1 — Stops Windows Search from sending queries to the web
*	ConnectedSearchUseWeb = 0 — Prevents Search from using web results
*	ConnectedSearchUseWebOverMeteredConnections = 0 — Also blocks web search on metered connections
*	BingSearchEnabled = 0 — Disables Bing integration in Windows Search
*	IsDynamicSearchBoxEnabled = 0 — Disables the animated/dynamic expanding search box on the taskbar
  
----📡 Telemetry & Privacy----
*	AllowTelemetry = 0 — Blocks Windows from sending diagnostic/telemetry data to Microsoft
*	DoNotShowFeedbackNotifications = 1 — Suppresses feedback request popups from Windows
*	EnableActivityFeed = 0 — Disables the Windows Timeline/activity feed feature
*	PublishUserActivities = 0 — Stops Windows from recording and publishing what you do across devices
*	UploadUserActivities = 0 — Prevents activity history from being synced to Microsoft's cloud
*	Start_TrackProgs = 0 (both HKLM & HKCU) — Stops Windows from tracking which apps you launch for Start menu suggestions
*	DiagTrack service Start = 4 — Disables the Connected User Experiences and Telemetry service
*	dmwappushservice Start = 4 — Disables the WAP Push Message Routing service (used for telemetry routing)
*	pla Start = 4 — Disables the Performance Logs and Alerts data collection service
*	Perflib Disable = 1 / Disable Performance Counters = 1 — Turns off Windows performance counter infrastructure, reducing overhead
  
----📢 Advertising & Location----
*	AdvertisingInfo Enabled = 0 (both HKLM & HKCU) — Disables the advertising ID used to track you across apps
*	DisabledByGroupPolicy = 1 (both HKLM & HKCU) — Enforces the advertising ID disable via policy
*	DisableLocation = 1 (LocationAndSensors) — Blocks all location services system-wide
*	DisableLocation = 2 (AppPrivacy) — Denies location access to all apps specifically
  
----🤖 AI & Copilot----
*	TurnOffWindowsCopilot = 1 — Completely disables Windows Copilot
*	ClickToDoEnabled = 0 (both HKLM & HKCU) — Disables the "Click to Do" AI action overlay feature
*	DisableAIDataAnalysis = 1 — Disables Windows AI (Recall) from analyzing and saving snapshots of your screen
*	WSAIFabricSvc Start = 4 — Disables the Windows AI Fabric background service
*	FeatureManagement Overrides (3895955085) — Force-enables a feature flag related to disabling Recall/AI features at the system level
  
----🌐 Microsoft Edge----
*	NewTabPageContentEnabled = 0 — Removes the news/content feed from Edge's new tab page
*	NewTabPageHideDefaultTopSites = 1 — Hides the default "top sites" suggestions on Edge's new tab page
*	StartupBoostEnabled = 0 — Disables Edge's startup boost (pre-launching in background)
*	AllowPrelaunch = 0 — Prevents Edge from pre-launching at Windows startup
  
----🎬 Game DVR / Xbox----
*	AllowGameDVR = 0 — Disables Game DVR via policy
*	GameDVR_Enabled = 0 — Disables Game DVR via the application manager setting
*	XblAuthManager, XblGameSave, XboxNetApiSvc, XboxGipSvc, xbgm — all Start = 4 — Disables all Xbox-related background services
  
----🖥️ UI & Explorer----
*	DisableSearchBoxSuggestions = 1 — (see Search section above)
*	DelayedDesktopSwitchTimeout = 5 — Reduces the delay when switching desktops/sessions
*	NoLockScreen = 1 — Removes the lock screen entirely, going straight to the login screen
*	ForceClassicControlPanel = 1 — Forces the old classic Control Panel instead of the Settings app
*	CLSID {86ca1aa0...} InprocServer32 = "" — Restores the classic Windows 10-style right-click context menu (removes the Windows 11 simplified menu)
*	DisallowShaking = 0 — Keeps the Aero Shake gesture enabled (shake a window to minimize others)
*	ExtendedUIHoverTime = 100ms — Sets the taskbar thumbnail hover delay to 100ms (faster preview popup)
*	MenuShowDelay = 150ms — Reduces the delay before menus appear on hover
*	TaskbarMn = 0 — Removes the Chat/Meet Now button from the taskbar
*	ScoobeSystemSettingEnabled = 0 — Disables the "suggested settings" nudge/prompts in Windows
*	DisableAcrylicBackgroundOnLogon = 1 — Removes the blurred acrylic/blur effect on the login screen
*	verbosestatus = 1 — Shows detailed status messages during startup and shutdown (e.g., "Starting services...")
  
----💾 File System----
*	NtfsDisableLastAccessUpdate = 1 — Stops NTFS from updating the "last accessed" timestamp on every file read, reducing disk writes
*	NtfsDisable8dot3NameCreation = 1 — Disables the legacy 8.3 short filename generation on NTFS, slightly improving file system performance
  
----🌐 Network----
*	Tcp1323Opts = 2 — Enables TCP window scaling for improved network throughput on fast connections
*	AllowIdlePowerdown = 0 — Prevents the network adapter platform from powering down during idle
*	DODownloadMode = 99 (0x63) — Sets Windows Update Delivery Optimization to use both LAN and internet peers for downloading updates
  
----🛑 Disabled Services----
These services are all set to Start = 4 (Disabled):
*	SysMain — Superfetch/memory preloading service
*	WSearch — Windows Search indexing service
*	Fax — Windows Fax service
*	lfsvc — Geolocation service
*	WpcMonSvc — Parental Controls monitor
*	RetailDemo — Retail demo mode service
*	SNMPTrap — SNMP network management trap service
*	Ndu — Windows Network Data Usage monitor
*	wisvc — Windows Insider Service
*	icssvc — Internet Connection Sharing (mobile hotspot)
*	PhoneSvc — Phone/SMS link service
*	AJRouter — AllJoyn Router (IoT device communication)
*	WMPNetworkSvc — Windows Media Player network sharing
*	PeerDistSvc — BranchCache peer distribution
*	SCPolicySvc — Smart Card removal policy
*	WalletService — Windows Wallet/payments service
*	DiagTrack — Telemetry & diagnostics (see above)
*	dmwappushservice — WAP push routing (telemetry)
*	pla — Performance Logs & Alerts
  
----⚙️ Miscellaneous----
*	MaintenanceDisabled = 0 — Keeps Windows automatic maintenance enabled (value 0 = not disabled)
*	AllowNewsAndInterests / AllowNewsAndInterets = 0 (both keys, one is a typo) — Disables the News and Interests widget on the taskbar
*	fDenyTSConnections = 1 — Disables Remote Desktop (RDP) connections to this machine
*	Windows Error Reporting Disabled = 1 — Stops Windows from generating and sending crash reports
*	DisableWindowsConsumerFeatures = 1 — Blocks Microsoft from silently installing suggested/sponsored apps
*	DisableConsumerAccountStateContent = 1 — Suppresses consumer-focused content in Windows (ads, tips, promotions)
*	DisableSoftLanding = 1 — Disables "soft landing" feature highlight tips shown to new users
*	NoDriveTypeAutoRun = 0xFF — Disables AutoRun on all drive types (USB, CD, network, etc.) for security
*	LetAppsRunInBackground = 2 — Denies all apps from running in the background (user-controlled per app)
*	FontCache service Start = 2 — Keeps the Font Cache service set to automatic (starts normally)

