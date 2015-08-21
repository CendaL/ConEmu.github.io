---
redirect_from:
 - /ru/LaunchNewTab.html

title: "ConEmu | Launch New Tab"

breadcrumbs:
 - url: TableOfContents.html#launch-apps
   title: Launch Apps
---

# Launching applications in ConEmu

* [Using ConEmu switches](#Using_ConEmu_switches)
* [Create new console dialog](#Create_new_console_dialog)
  * [Create new console without dialog](#Create_new_console_without_dialog)
* [Tasks](#Tasks)
* [Create new tab from existing one](#Create_new_tab_from_existing_one)
* [Duplicate root](#Duplicate_root)
* [Default terminal feature](#Default_terminal_feature)
* [Attach existing console or GUI application](#Attach_existing_console_or_GUI_application)
* [Attach from command prompt](#Attach_from_command_prompt)
* [Automatic attach of cmd](#Automatic_attach_of_cmd)
* [Gui Macro](#Gui_Macro)



<h2 id="Using_ConEmu_switches"> <a href="ConEmuArgs.html">Using ConEmu switches</a> </h2>

When you run something from `Win+R` or shortcut from your Desktop,
you may use `-cmd` or `-cmdlist` to run your application. Remember, `-cmd` or `-cmdlist` will be the last ConEmu's GUI interpreted switch. The rest of command line will be used to start your application. Read more in the [wiki](ConEmuArgs.html). Example:

~~~
ConEmu -reuse -dir "c:\projects" -cmd "set PATH=C:\MinGW\bin;%PATH%" & chcp 65001 & sh -l -i 
~~~


<h2 id="Create_new_console_dialog"> Create new console dialog </h2>

How to start application (tcc, powershell, far, putty) in ConEmu tab?

![ConEmu confirmation of new console creation](/img/ConEmuCreate.png)

This dialog may be opened from:

* Keyboard (Win+W by default), or
* ![Toolbar](/img/ConEmuAddBtn.png)
* ![System menu](/img/ConEmuAddSys.png)
* GuiMacro [Create(0,1)](GuiMacro.html#Recreate)

Well, what you can do with this dialog?

* Choose command line and startup directory for new process.
  You may use environment variables in both fields.
  Also, you may choose from drop down list either any of predefined
  [tasks](Tasks.html) or any command from history.
* Choose another user name and password,
  ‘Restricted current user’ account or ‘Run as administrator’ feature.
* You may split active tab vertically or horizontally.
* And it is possible to start new tab in the new ConEmu window,
  new `ConEmu.exe` process will be started.
* Dialog's system menu contains ‘Reset command history’ menu item.

Similar dialog may be opened when you [Restart current console](RestartTab.html).



<h3 id="Create_new_console_without_dialog"> Create new console without dialog </h3>

You may switch off create new console confirmation,
just disable ‘Create confirmation’ checkbox on the
[Appearance](Settings.html#Appearance) settings page.

**NB** You may pop up confirmation dialog even if ‘Create confirmation’ unchecked.
Just hold Shift while creating console from toolbar, System menu,
or Keyboard (`Win+Shift+W` by default).



<h2 id="Tasks"> <a href="Tasks.html">Tasks</a> </h2>

You may define your own tasks or just use predefined one.
Choose the task from drop down menu or run task by hotkey.
You may choose task in the ‘Create new console’ dialog too.



<h2 id="Create_new_tab_from_existing_one"> Create new tab from existing one </h2>

Use [-new_console](NewConsole.html) switch while executing command.
For example, if you want to start PuTTY in new ConEmu tab,
type in command prompt (`cmd.exe` started in ConEmu tab)

~~~
putty -new_console
~~~

and it will be launched in the new tab of ConEmu.

`-new_console` works even in batch files.

**NB** Option [Inject ConEmuHk](ConEmuHk.html) must be turned on [Settings / Features](SettingsFeatures.html).



<h2 id="Duplicate_root"> Duplicate root </h2>

Well, this interesting feature offers a way to duplicate shell
([root process](RootProcess.html) of current tab) state to the new ConEmu tab.
For example, you have started `cmd.exe`, set up environment variables,
cd somewhere, run any program (vim for example) and call ‘Duplicate root’
from tab popup menu.

This will create ‘copy’ of `cmd.exe` at most recent state (when possible).




<h2 id="Default_terminal_feature"> Default terminal feature </h2>

This allows to seize creation of console processes from many (selected by user) applications.
For example, when you run ‘Command prompt’ shortcut from ‘Start menu’ cmd.exe
may start in the new ConEmu tab.

Read more about [Default terminal feature](DefaultTerminal.html).



<h2 id="Attach_existing_console_or_GUI_application"> Attach existing console or GUI application </h2>

Choose ‘Attach...’ from [system menu](SystemMenu.html).



<h2 id="Attach_from_command_prompt"> Attach from command prompt </h2>

Batch file `Attach.cmd` is shipped with ConEmu package.
Run this file from any cmd.exe to attach this console into the new ConEmu tab.
This batch just run following command

~~~
ConEmuC.exe /ATTACH /NOCMD
~~~

which you may run from any other console shell or even from your own console application.



<h2 id="Automatic_attach_of_cmd"> Automatic attach of cmd </h2>

Mostly like as ‘Attach from command prompt’ but you may set up automatic execution
of ‘Attach’ on cmd.exe startup.
This also works with TCC/LE.

Set up feature on ‘ComSpec’ page of ‘Settings’ dialog.



<h2 id="Gui_Macro"> Gui Macro </h2>

You may set up several most used shells or build environments via [GuiMacro](GuiMacro.html).
Example: open ‘Keys & Macro’ settings page, click ‘Macros’ radio (it filters long key list)
and in the free ‘Macro XX’ slot type

~~~
shell("","C:\Windows\System32\cmd.exe /E:ON /V:ON /T:0E /K ""C:\\Program Files\\Microsoft SDKs\\Windows\\v7.1\\Bin\\SetEnv.cmd"" /Release /x86")
~~~

choose any wanted hotkey (`Ctrl+Shift+1` for example) and **Save settings**.
