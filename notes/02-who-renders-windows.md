# Who is the Keeper?

I want to know who has all the info about the windows rendered on screen. Once I know it, I can either request or change or write code at that level.

## Configuration
- OS -> Linux archlinux 6.12.61-1-lts
- Window Manager -> Hyprland
- Display Server Protocol -> wayland

## How do I Begin
In order to know who manages windows, I had to understand some of the following terms

- Desktop Environment
- Window Manager
- Compositor
- Display Server
- IPC: Inter Process Communication
- Unix Domain Sockets

Wayland is a protocol. Wayland compositor is the implementation of that protocol. Hyprland is one such example of compositor. And hyprland is a bundled Compositor+window manager. There are standalone compositors also, and there are bundled also like GNOME with Mutter.

So, In my case, hyprland knows it all.

## What are the ways to get the info

Now I need to know what are the ways to get info from hyprland?

### hyprctl

I found something called `hyprctl`. hyprctl is an utility for controlling some parts of the compositor from a CLI or a script.

```bash
hyprctl clients
```

I can use this command to list all the details about all the rendered windows.
Example:

```
Window 5f45642baf10 -> 02-who-renders-windows.md - vats - Visual Studio Code:
	mapped: 1
	hidden: 0
	at: 1926,6
	size: 2548,1428
	workspace: 2 (2)
	floating: 0
	pseudo: 0
	monitor: 1
	class: code
	title: 02-who-renders-windows.md - vats - Visual Studio Code
	initialClass: code
	initialTitle: Visual Studio Code
	pid: 11568
	xwayland: 0
	pinned: 0
	fullscreen: 1
	fullscreenClient: 1
	grouped: 0
	tags: 
	swallowing: 0
	focusHistoryID: 1
	inhibitingIdle: 0
	xdgTag: 
	xdgDescription: 
```