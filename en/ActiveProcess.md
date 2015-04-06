---
redirect_from: /ru/ActiveProcess.html

title: "ConEmu | Active Process"

description: "Active Process is a shell or current console tool"

bc1_url: TableOfContents.html#terms
bc1_title: ConEmu

bc2_url: ConEmuTerms.html
bc2_title: Terms
---

{% raw %}

# Active Process

*Active Process* in most cases is the latest process run in the console.
That is your shell (cmd, powershell, bash) if you are in the prompt, and current console tool during
some command execution (perl, git, ssh, etc.)

![Active process in ConEmu StatusBar](/img/ConEmuActiveProcess.png)

You can see *Active Process* name, bitness and PID in the [StatusBar](StatusBar.html)
or in the [TabBar](TabBar.html) if you choose appropriate [Tab template](SettingsTabBar.html).
For example template `%s {%p}` will show `timeout {21564}`.

**Note** *Active Process* is **console** process or
[ChildGui](ChildGui.html) application,
but is neither `ConEmu[64].exe` nor `ConEmuC[64].exe`.

{% endraw %}
