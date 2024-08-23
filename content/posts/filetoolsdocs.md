---
title: "File Tools Documentation"
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


Tools for various file handling interactions

#### Legend:
 !TBD: marks anything To Be Deleted in upcoming update (redundant things that still exist)

---

### Function: `clean_file_open`

Read or Write to file with truncate option.

#### clean_file_open Signature

```python
def clean_file_open(
    filepath, readOrWrite, writingContent, extraWarn, truncate
) -> None:
```
### Parameters
- `filepath` (string)
- `readOrWrite` (string / char)
- `writingContent` (optional: string) 
    - Required if using `w` option for `readOrWrite` argument.
- `extraWarn` (optional: string)
- `truncate` (optional: bool)

---
### Function: `wait_for_file`

Waits until specified filepath is created.

#### wait_for_file Signature

```python
def wait_for_file(path, tries) -> bool :
```
### Parameters

- `path` (string)
- `tries` (optional: int)

---
### Function: `clean_mkdir`

Makes a directory if it doesn't already exist, avoids throwing exception. 

#### clean_mkdir Signature

```python
def clean_mkdir(dirpath) -> bool :
```
### Parameters

- `dirpath` (string)

---
### Function: `clearDirPath`

Will DELETE a directory path, obviously use with extreme caution.

#### clearDirPath Signature

```python
def clearDirPath(path) -> bool :
```
### Parameters

- `path` (string)
---
### Function: `copy`

Copy target file to destination

#### copy Signature

```python
def copy(target, dest) -> None :
``` 
### Parameters

- `target` (string)
- `dest` (string)
---
### Function: `switchdirpath`

Changes the first directory found in a path to the given directory.

#### switchdirpath Signature

```python
def switchdirpath(fullpath, destdir) -> str :
``` 
### Parameters

- `fullpath` (string)
- `destdir` (string)
---
### Function: `is_file_contents_int`

Checks if the file contents is an integer value.

#### is_file_contents_int Signature

```python
def is_file_contents_int(file_path) -> bool :
```
### Parameters

- `file_path` (string)
---
