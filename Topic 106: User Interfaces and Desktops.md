# TOPIC 106: User Interfaces and Desktops

Reference: LPIC-1 Objectives V5.0: https://wiki.lpi.org/wiki/LPIC-1_Objectives_V5.0

## Covered Key Areas (weighted)

- **106.1 Install and configure X11** *(Weight: 2)*
- **106.2 Graphical desktops** *(Weight: 1)*
- **106.3 Accessibility** *(Weight: 1)*

## Numbered Table of Content

1. TOPIC 106: User Interfaces and Desktops
   1. 106.1 Install and configure X11
   2. 106.2 Graphical desktops
   3. 106.3 Accessibility

---

## 106.1 Install and configure X11

### Key Areas

- Understand X11 architecture (display server, clients, display manager).
- Configure display settings, keyboard, and input devices.
- Manage remote graphical access concepts and secure forwarding options.
- Diagnose common X11 startup/configuration issues.

### Key Commands

```format
X
Xorg
xwininfo
xrandr
xdpyinfo
xhost
startx
```

### Key Paths

```format
/etc/X11/xorg.conf
/etc/X11/xorg.conf.d/
~/.xinitrc
~/.Xresources
```

### Summary

Know the core X11 model and practical display/input configuration. Focus on identifying components and using diagnostic tools.

### Possible Exam Questions

1. What is the role of the X server compared to an X client?
2. Which command lists and changes display resolutions at runtime?
3. Where are per-user X session startup commands commonly configured?
4. Why is unrestricted `xhost +` insecure?

---

## 106.2 Graphical desktops

### Key Areas

- Understand desktop environment components and session lifecycle.
- Configure display manager behavior and default session selection.
- Recognize resource and package differences among major desktop stacks.

### Key Commands

```format
systemctl
loginctl
x-session-manager
update-alternatives
```

### Key Paths

```format
/etc/X11/default-display-manager
/usr/share/xsessions/
~/.xsession
~/.config/
```

### Summary

This objective emphasizes desktop/session fundamentals rather than deep GUI tuning. Be ready to identify where sessions are defined and how display managers start them.

### Possible Exam Questions

1. What is the difference between a display manager and a desktop environment?
2. Where are available X sessions typically described?
3. How can a system boot into a graphical target with systemd?
4. Which user file can define startup commands for a graphical session?

---

## 106.3 Accessibility

### Key Areas

- Identify Linux desktop accessibility features for vision, hearing, and mobility.
- Configure high-contrast themes, screen readers, and keyboard navigation aids.
- Understand the purpose of assistive technology frameworks in desktop stacks.

### Key Commands

```format
gsettings
dconf
orca
```

### Key Paths

```format
~/.config/dconf/
/usr/share/themes/
/usr/share/icons/
```

### Summary

Low exam weight but important conceptually: know where accessibility options are configured and which common tools provide assistive features.

### Possible Exam Questions

1. Name one common screen reader used in Linux desktops.
2. What setting area is used for high-contrast visual accessibility?
3. Why are keyboard-only navigation features important in accessibility?
4. Which command-line tools are commonly used to adjust desktop settings schemas?
