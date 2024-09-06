---
title: "Process Tools Documentation"
date: 2024-08-18T19:38:36-05:00
draft: true
# weight: 1
# aliases: ["/first"]
tags: ["Security", "Documentation", "Docs"]
author: "Atomic Analog Developers"
# author: ["Me", "You"] # multiple authors
showToc: false
TocOpen: false
draft: false
hidemeta: false
comments: false
description: "AtomicAPI Documentation"
canonicalURL: "https://canonical.url/to/page"
disableHLJS: true # to disable highlightjs
disableShare: true
disableHLJS: false
hideSummary: true
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: false
#cover:
#    image: "https://cdn.iconscout.com/icon/free/png-512/free-atom-31-117013.png?f=avif&w=512&h=512" # image path/url
#    alt: "<alt text>" # alt text
#    caption: "<text>" # display caption under cover
#    relative: false # when using page bundles set this to true
#    hidden: false # only hide on current single page
editPost:
    URL: "https://github.com/<path_to_repo>/content"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link


---

Tools for managing active processes 

#### Legend:
 !TBD: marks anything To Be Deleted in upcoming update (redundant things that still exist)

---

### Function: `pid_by_name`

returns a PID (Process ID) by the process name 
#### pid_by_name Signature

```python
def pid_by_name(procName) -> bool or int :
```
### Parameters
- `procName` (string)

---

### Function: `kill_proc_tree`

Kills a process tree, meaning all children of parent process, by it's PID

#### kill_proc_tree Signature

```python
def kill_proc_tree(
    pid, sig, include_parent,
    timeout, on_terminate
) -> ([psutil.Process], [psutil.Process]) :
```
### Parameters
- `pid` (int)
- `sig` (optional: signal)
- `include_parent` (optional: bool)
- `timeout` (optional: int)
- `on_terminate` (optional: def)

---
