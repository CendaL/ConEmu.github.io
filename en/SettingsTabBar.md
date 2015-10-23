---
redirect_from:
 - /ru/SettingsTabBar.html

title: "ConEmu | Settings › TabBar page"

breadcrumbs:
 - url: TableOfContents.html#settings
   title: Settings
---

# Settings: Tabs

*This page was generated automatically from ConEmu sources*
{% comment %} IDD_SPG_TABS {% endcomment %}

![ConEmu Settings: Tabs](/img/Settings-TabBar.png)



## Tabs (consoles, Far Manager panels/editors/viewers)




* **Always show**
* **Auto show**
* **Don't show**


#### Tabs on bottom  {#id2481}


#### Internal CtrlTab  {#id1531}
Handle CtrlTab and CtrlShiftTab internally (by ConEmu). These keystrokes will not be sent to console window, but You can easily switch between consoles (panels).

#### Lazy tab switch  {#id1532}
When checked - real window switching will be performed on Ctrl depress

#### Recent mode  {#id1533}
Switch first between recent tabs. You may still switch between tabs in standard manner using Left/Right (after CtrlTab), while Ctrl is still presses.

#### Hide disabled tabs  {#id2051}
Hide tabs, wich can't be activated. E.g. hide Far Manager editors while executing cmd.exe

#### Far windows  {#id2053}
Show all Far Manager windows (panels, editors, viewers) instead of one tab for one console

#### ‘Host-key’+Number iterates Far windows  {#id2104}
Iterate opened Far windows with ‘Host-key’+Number

#### Active console only  {#id1642}
Show tabs from active console only

#### One tab per group  {#id2599}
Show only one tab for all splits in the group

#### Activate split on mouse hover  {#id2601}
When several panes (splits) are visible simultaneously activate console with mouse over, 3rd-state - match ‘Active window tracking’ system settings

LTEXT



RTEXT



#### Tab templates (Far Manager ones are located on 'Far Manager' page)  {#id2106}






LTEXT



#### Console
Common tab template (any console program except Far Manager)

#### Modified suffix
When something was changed in the inactive console ConEmu may show that in the tab label Set or clear this suffix appended to the tab template

#### Invisible tab activity flash count
When something was changed in the inactive console ConEmu may flash tab icon in that case Set ‘-1’ to flash infinitely Use odd values to leave tab in highlighted state

#### Skip words from title


#### Maximum tab width (in chars)


#### Admin shield  {#id2109}
When this is checked - ‘Shield’ icon will be shown in tabs, started ‘As administrator’

#### suffix  {#id2110}
When this is checked - specified suffix will be appended in tabs titles, started ‘As administrator’. You may choose insertion place with ‘%a’ var, otherwise suffix will be at the tab end.



LTEXT



LTEXT



RTEXT



When you double click on the tab...

When you double click on the free space of tab bar... ‘Auto’ means ‘Maximize/Restore’ when caption is hidden and ‘Open new shell’ when caption is visible

