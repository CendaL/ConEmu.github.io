---
redirect_from:
 - /ru/CommandLine.html
 - /en/commandline.html
 - /ru/commandline.html

title: "ConEmu | CommandLine - GUI, Console and Shells switches"

breadcrumbs:
 - url: TableOfContents.html#launch-apps
   title: Launch Apps
---

# CommandLine - GUI, Console and Shells switches

There are several places where you may need to use command line
arguments. Do not confuse them. The switch from one group will not
be working in the another place!

* [GUI args](#ConEmuArgs)
* [ConEmuC args](#ConEmuC)
* [Shell args](#Shell_args)
* [Console args](#Console_args)
* [Task parameters](#Task_parameters)



<h2 id="ConEmuArgs"> <a href="ConEmuArgs.html">GUI args</a> </h2>

These switches are used for changing ConEmu window behavior or
running specific commands (shells) in the ConEmu's tabs or splits.
In the following example all between `ConEmu` and `-cmd` are GUI
arguments.

~~~
ConEmu -mintsa -config "Maintainance" -dir "C:\Project" -cmd git fetch
~~~



<h2 id="ConEmuC"> <a href="ConEmuC.html#ConEmuC.exe_command_line_switches">ConEmuC args</a> </h2>

ConEmuC is a console part of ConEmu. It serves a console window
acting a console server in the ConEmu-ConEmuC pair. Also, it can be
used to run some checks (do your console is run in ConEmu, etc.), to
execute [GuiMacro](GuiMacro.html)'s, to make
[MemoryDump](MemoryDump.html)'s, and so on.

~~~
ConEmuC -isconemu & if errorlevel 2 (echo Not in ConEmu) else if errorlevel 1 (echo In ConEmu)
~~~

~~~
ConEmuC -GuiMacro:0 print "Echo abc\n"
~~~



<h2 id="Shell_args"> Shell args </h2>

Generally speaking, ConEmu has no common with shells. The shell, is
what you run in the ConEmu's tab or split. Read more here:
[LaunchNewTab](LaunchNewTab.html).

~~~
cmd /k ver & your_batch_script.cmd
~~~

~~~
powershell -NoProfile -NoExit -Command "Import-Module List.ps1 -ArgumentList 'Tasks'"
~~~

~~~
bash.exe --login -i
~~~



<h2 id="Console_args"> Console args </h2>

That is much like as ‘Shell args’, with only difference that ConEmuC can process some commands internally, before running you shell: ‘set’, ‘chcp’, ‘title’. They can be used in [Tasks](SettingsTasks.html), after ‘-cmd’ ConEmu's switch and so on.

~~~
"set PATH=C:\MinGW\bin;%PATH%" & set MSYSTEM=MINGW64 & chcp 65001 & sh -l -i
~~~


<h2 id="Task_parameters"> Task parameters </h2>

When you do configure [tasks](SettingsTasks.html)
you will see ‘Task parameters’ edit field.
That is the place to:

* force the task to be run in the special directory;
* give the started tab a specific icon;
* when used from the jump list force the task to be run in the existing ConEmu window.
