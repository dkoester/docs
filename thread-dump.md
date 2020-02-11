### thread dump process:

1. Find the PID of the java process -> server mgmt -> tools -> resource monitor > java.exe (get this PID)
2. Make sure the java bin is on the environment path ... env variables(search) -> environment varibles -> select PATH and edit -> java bin directory (jdk) should be here.
3. open command prompt -> run "jstack <PID> > thread_dump.txt"

#### analyzer tools
- [fasterthread](https://fastthread.io/) - free tool with graph, charts, and easy to identify sections.
- [spotify](https://spotify.github.io/threaddump-analyzer/) - free spotify basic analyzer more of a text based tool but still useful
