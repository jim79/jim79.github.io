---
title: End-of-line characters - LF, CR/LF
permalink: /end-of-line-character/
layout: single
---

## New line 
A *newline*, also known as a line break or end-of-line (EOL) character, is a special character or sequence of characters used to indicate the end of a line of text. It is commonly used in computing and programming to separate lines of code or text.

**Windows uses the combination ```\r\n``` (also known as CR/LF (Carriage Return and Line Feed)) to denote the new line character** 

**Unix-like systems use ```\n``` (LF (Line Feed)) to denote the new line character**

_Python code written on Windows can generally run on Linux systems, as Python is cross-platform. Most Python interpreters solve the end-of-line differences automatically. But scripts with DOS (Windows) line endings can cause issues in bash scripts or when read as plain text files._

#### You can use tools like ```dos2unix and unix2dos``` to convert line endings of bash scripts and text files.

## VS Code
### Setting the end-of-line character in VS Code
You can set the end of line character for the current project in VS Code with a simple click (see video below)

[Setting the end-of-line character in VS Code](https://youtu.be/-ZImIZK_PTU)

### Set the end-of-line character globally in VS Code
You can globally configure the end-of-line (EOL) character in Visual Studio Code (VS Code) by adjusting its settings as summarized below:

1. Open Settings:
   - Click on the **gear icon** in the bottom-left corner of VS Code and select **Settings**.
   - Alternatively, press ```Ctrl + ,``` (Windows/Linux) or ```Cmd + ,``` (Mac).

2. Search for EOL Setting:
   - In the search bar at the top of the Settings window, type **"end of line"**.

3. Set the Default EOL:
   - Look for the setting **`Files: EOL`**.
   - From the dropdown, choose:
     - **LF**: Line Feed (`\n`) — Common for Linux/macOS.
     - **CRLF**: Carriage Return + Line Feed (`\r\n`) — Common for Windows.

4. Save the Setting:
   - The change is automatically saved and will apply globally for all new files created in VS Code.

## Git and end-of-line character
What about code you clone from a Git repo or the code that you push to a Git repo ?

The default end-of-line (EOL) setting in Git depends on the operating system and whether specific configurations like ```core.autocrlf``` or ```.gitattributes``` have been set.

### Default Behavior
1. Without Configuration (No ```core.autocrlf``` or ```.gitattributes```):
   - Git **stores files with their original line endings** as they are added to the repository.
   - There is **no automatic normalization** or conversion of EOLs during commits or checkouts.

2. **When ```core.autocrlf``` Is Not Set:**
   - Git does not modify line endings. It will use whatever EOLs exist in the working directory files.

### **Operating System Influence**
- **Windows:**
  - Many developers enable ```core.autocrlf=true``` to convert LF (repository) to CRLF (working directory) and vice versa.
- **Linux/macOS:**
  - Most developers leave ```core.autocrlf``` unset or set it to ```input``` for minimal interference, ensuring files in the repository use LF.

### **Key Takeaways**
- The **default behavior** is no EOL normalization unless explicitly configured with `core.autocrlf` or `.gitattributes`.
- To ensure consistent line endings in a collaborative environment, it's best to use a ```.gitattributes``` file to define EOL policies explicitly. 

For example:
```text
* text=auto
```
This normalizes text files to LF in the repository and applies platform-specific EOLs on checkout.

For a brief history and Normalizing Line Endings in Git read this article.\
[CRLF vs. LF: Normalizing Line Endings in Git](https://www.aleksandrhovhannisyan.com/blog/crlf-vs-lf-normalizing-line-endings-in-git/#line-endings-in-git)

