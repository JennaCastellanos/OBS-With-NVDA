# OBS Studio With NVDA

This is a guide designed to help blind NVDA users navigate and use OBS Studio for Windows.

## Assumptions

- You are using Windows 10 or newer
- You are using OBS Studio 30.0.2 or newer
- You are familiar and confident with the controls and operation of Windows and NVDA (NV-Access)
- You are familiar with the basics of Windows Narrator to perform certain actions such as connecting a Twitch account for streaming (not required for most of the app)
- You have a number pad (tenkey) or use ObjPad or otherwise have access to NVDA object navigation and are comfortable using it heavily
- you are capable of and comfortable with troubleshooting accessibility blockers

## Resources

- [NV-Access](https://www.nvaccess.org/)
- [NVDA User Guide](https://www.nvaccess.org/files/nvda/documentation/userGuide.html)
- [ObjPad](https://addons.nvda-project.org/addons/objPad.en.html)
- [OBS Studio](https://obsproject.com/)
- [Complete guide to Narrator](https://support.microsoft.com/en-us/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1)

## definitions and terminology

This guide will use certain words, phrases, and symbols. They are listed as follows:

- keyboard and keyboard shortcuts
  - `+` (plus): press all keys in a keystroke connected by a plus symbol simultaneously
  - `,` (comma): press the next key separately from the previous keys in the keystroke combination
  - `>` (greater than): indicates selecting an option or submenu within a menu
  - ctrl: control
  - win: windows key
  - NVDA: contextual. When used in a key combination, it signifies the NVDA modifier key (usually insert and/or caps lock)
  - numpad: key prefix. Signifies that the key being pressed is on the number pad (e.g numpad 7, numpad slash)
- Window or dock: a section of the OBS interface, either part of the primary app or displayed visually as a floating pane on top of the main app.
- Source: a media component (video, audio, image, browser, external) that OBS can display on the canvas.
- Scene: A collection of sources which can be switched to depending on which media is desired.

## Important note on using object navigation and the review cursor

All instructions given in this guide rely on the object order presented by NVDA's object navigation. Tabbing through the interface will present different options in a different order. In some circumstances, tab navigation is preferred over object navigation. Unless otherwise specified, assume object navigation is being used. In some cases, further keystrokes are required to interact with the navigator object either by moving the current focus to the current navigator object or moving the mouse to the current navigator object and then simulating a left mouse click.

## Introduction

OBS Studio is open-source software for recording and broadcasting. It's commonly used to stream to websites like Twitch and YouTube. It's very powerful, but its accessibility is not very good, however it is useable. In fact, many blind and visually-impaired people use it regularly to stream. Operation with a screen reader is very different between Mac OS and Windows. This guide will specifically cover the use of OBS on a Windows machine. You must be okay with the fact that you may need sighted assistance at some point. Some operations, like positioning elements on the canvas cannot be done with NVDA, and you will need a sighted person to help you. Fortunately, the basics can be done entirely without sight.

## first-time setup

When you first run OBS, you should be automatically placed into the auto configuration wizard. If you are not, you can find it under tools in the menu with `alt + t > auto configuration wizard`.

The setup wizard consists of form elements that you can tab and arrow through. Configure your settings as desired and proceed through the  setup wizard by following the instructions and prompts. If you configure a streaming service such as Twitch, it is strongly recommended that you log in instead of using a stream key. OBS obfuscates it by default, however sharing that key will allow anybody to stream as you. In order to log into Twitch, you must switch to Windows Narrator as NVDA does not work with the OAuth prompt that appears. Use scan mode, tabbing, and arrow navigation as needed to navigate to the password prompt. Once signed in, OBS will return you to the setup wizard and you may proceed.

Once the wizard completes, apply the settings and continue. You may not be immediately placed in the main app and instead are placed in a window such as "chat" or "stream stats". This is normal and expected. OBS can show several windows or docks that provide users additional information about the current recording or stream. While they provide a lot of relevant data, they are not accessible to NVDA users and as such are not useful and also present a substantial hindrance to blind users.  If NVDA does not announce a window title similar to "OBS 30.0.2 - Profile: Untitled - Scenes: Untitled", you may attempt to press `alt + f4` to close the window. a confirmation prompt will appear confirming you wish to close that window. To prevent unnecessary windows/docks from opening next time, enter the docks menu with `alt + d` and ensure that only the following items are checked:

- Scenes
- Sources
- Audio mixer
- Scene transitions
- Controls

## Interface description

### Overview

The main OBS window consists of several windows as navigated via object navigation:

1. Menu bar
2. Status bar
3. Scenes
4. Sources
5. Audio mixer
6. Scene transitions
7. Controls

### Menu bar and status bar

The menu bar is most easily accessed by pressing alt to navigate the menus. It functions as any other menu bar would.

- file. `alt + f`. Settings, recording and settings folder shortcuts, general settings, etc.
- edit. `alt + e`. Copy, paste, scene properties, transform, undo/redo, etc.
- view. `alt + v`. App v8ew controls, status bar visibility, reset UI, etc.
- docks. `alt + d`. Manage additional UI windows, reset docks, etc.
- profile. `alt + p`. Select and manage recording profiles.
- scene collection. `alt + s`. Create, edit, and manage collections of scenes.
- tools. `alt + t`. Miscellaneous tools like captions and web sockets.
- help. `alt + h`. Help options.

The status bar is not particularly useful for NVDA users, however it allows you to monitor CPU utilization and framerate.

### Scenes and Sources

These windows are structurally and functionally very similar. Sources control what will be displayed on the canvas and in what order. Scenes allow you to have different groupings of sources that you can quickly switch between depending on what you want to appear on the canvas.

Both windows include a list, a toolbar, and a float button. The list displays scenes and sources in descending order from front to back. The order of sources determines which media source appears at the front of the canvas. The order of scenes determines which scene is selected when using keyboard shortcuts. Items at the top of the list will appear first. The selected source and scene will be the subjects of focus when using edit and property controls.

The menu bar in both windows allows you to create, delete, modify, and reorder your scenes and sources. They will be discussed in further detail later. The float button allows you to detach from the main window. This guide will not cover the float button.

### Audio Mixer

This window allows you to control all audio sources in a scene. If there are no audio sources present, this list will be empty. An audio source will be listed in the following order: audio properties, name, volume (measured in dB), volume slider, mute checkbox.

After the sources, you will find a menu bar and float button, similar to the previous windows. The menu bar allows you to control advanced audio properties such as pan, audio delay, and multitrack output. This properties window also makes it significantly easier to adjust the volume level of a selected source.

### Scene Transitions

This window controls how OBS will visually transition between scenes when they are switched. In order:transition combo box, duration text, duration spin button, add configurable transition button, and a float button.

The transition combo box controls the visual scene transition. By default, it can be set to cut or fade and more can be added via the add configurable transition button. The duration spin button will control the duration of the transition. By default, it is set to 1000 milliseconds, the equivalent of 1 second.

### Controls

This window allows you to make recordings, start and stop streaming, toggle studio mode, open the settings pane, and exit. In order: start streaming checkbox, start recording checkbox, studio mode checkbox, settings button, exit button, start virtual camera checkbox, and a float button

Visually, the checkboxes here are presented as buttons, and they can be activated with the space bar.
The start recording checkbox will record the canvas to a file on your local machine. The start streaming checkbox will start and stop a livestream to your streaming service, provided that it has been configured correctly.
The studio mode checkbox will give you access to a preview window and a program window. This enables you to make edits to your scene and preview the scene you plan on switching to before pushing it to the program window. It is most helpful when livestreaming, but it offers few advantages to NVDA users since it is a visual preview.
The settings and exit buttons will open the settings window and exit OBS Studio, respectively.
Start virtual camera checkbox will let you use the virtual camera feature and display your active scene in any app that accepts a camera input such as Zoom or Google Meet.
