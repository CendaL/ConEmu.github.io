---
title: "ConEmu | Tasks"

description: "ConEmu's Tasks are simple way to store oft-used shells,
  start several shells in tabs or splits."

breadcrumbs:
 - url: TableOfContents.html#launch-apps
   title: Launch Apps
---

# ConEmu's Tasks

ConEmu-Maximus5 is a terminal or a kind of container
for whatever programs you might want to run inside it:
[console applications](ConsoleApplication.html)
or simple programs with self graphical interface
([ChildGui](ChildGui.html)).
They are typically a [shells](TerminalVsShell.html)
like cmd.exe, bash.exe, powershell.exe,
editors like notepad++ or even another terminals
like mintty.exe or PuTTY.exe.

And ConEmu has [tabs](TabBar.html) and [splittings](SplitScreen.html)
(à la screen/tmux, but handled at the GUI level).
So you can have different programs running in each of those ‘slots’.

A ‘task’ is an instruction what and how ConEmu must run in ‘slots’.
Each ‘task’ has a ‘name’, one or more actual commands to run,
‘hotkey’ to run task which is available when ConEmu has focus,
some optional switches like startup directory or icon.

| Value    | Example |
|:---------|:--------|
| task name | {Git Bash}, {WinSDK v7.0}, ... |
| name or full path to [program](https://wikipedia.org/wiki/Executable) | bash.exe |
| program arguments | --login -i |
| [-new_console](NewConsole.html) switch(es) | -new_console:t:"Bash" -new_console:d:"C:\Projects" |
| several [tabs](TabBar.html) or [splits](SplitScreen.html) | cmd <br/> powershell -new_console:sV |

When you need to [create a tab](LaunchNewTab.html)
you may type may be long and full command line like

```
set "FARHOME=" & C:\Far\Far.exe /w /x /p%ConEmuDir%\Plugins\ConEmu;%FARHOME%\Plugins;C:\Far\Plugins.My
```

Or just run task named `{Far}`.

At last, Tasks are the only easy way to run several [tabs](TabBar.html)
or preconfigured [splits](SplitScreen.html) at once.

### Bottom line

Use ‘Tasks’ to run predefined commands anytime by name or hotkey.

![ConEmu's tasks dropdown](/img/ConEmuStartTask.png "Start task dropdown menu")

Tasks may be configured in the [‘Settings’ dialog](SettingsTasks.html).


<h2 id="create-new-task"> Creating new task </h2>

When you want to create new task absent in the default tasks list you need to know:

* The shell name. For example: cmd, powershell, bash and so on.
* The shell arguments. For example: `/k vcvarsall.bat x86`
* Shell working directory. That may be very significant.
* In some cases you need to know environment variables.


<h3 id="find-required-information"> Where you may get required information? </h3>

In most cases you may open properties of shortcut created by any installer.
Just find the shortcut, right-click it, and choose ‘Properties’.

![VS tools prompt](/img/ConEmuVsTask1.png "Searching for VS tools prompt command")

* Copy ‘Target’ contents to the ‘Task Commands’;
* Optionally set working directory with <code>/dir</code> switch in the ‘Task parameters’;
* If you want to choose specific tab name use [-new_console:t:"VS 12.0"](NewConsole.html) switch;
* Finally, if you need to define some environment variables, just specify them before the shell.

~~~
set Var1=Value1 & set "Var2=Value with spaces" & cmd /k vcvarsall.bat x86 -new_console:t:"VS 12.0"
~~~

Finally, the task for VS prompt is ready.

![ConEmu VS tools prompt](/img/ConEmuVsTask2.png "ConEmu task for VS tools prompt")


<h3 id="if-no-shell-shortcut"> If there is no shortcut for that shell </h3>

Sometimes, if the shell is started from another program you may use
[ProcessExplorer](ProcessExplorer.html) or [ProcessMonitor](ProcessMonitor.html)
to detect which command is started, arguments and the working directory.

If you can't do that, just google for alternatives.
For example it is hard to find proper arguments for NuGet console
started from Visual Studio because VS do not start `powershell.exe`
but run powershell host internally. Just google! For example:

* [Using NuGet standalone command-line](http://headsigned.com/article/using-nuget-standalone-command-line)
* [Download Nuget Packages Without VS/NuGet Package Manager](http://stackoverflow.com/a/13581202/1405560)
* [Do an offline installation into Visual Studio](http://stackoverflow.com/a/15000559/1405560)
