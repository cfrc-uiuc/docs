This is just a place to record useful computer/desktop tips and tricks.

## Linux

### General

#### Virtual Consoles

Virtual consoles are text-mode...uhh...virtual consoles that are
accessible outside the normal graphical desktop. These may be used to
rescue your system in instances of more severe graphical crashes. These
virtual consoles may be accessed with keyboard shortcuts, normally
Ctrl+Alt+F3 through Ctrl+Alt+F6. In Fedora Linux, the second virtual
console shortcut (Ctrl+Alt+F2) is reserved for the graphical session,
generally.

Here's a simple example of using a virtual console to restart a crashed
X session (please note that this is for reference mostly, and hopefully
isn't something you should have to do with any frequency):

1.  Press Ctrl+Alt+F3 to access a virtual console.
2.  You will be presented with a login prompt on the virtual console.
    Log in with your normal username and password.
3.  Run `sudo systemctl restart sddm ; exit` (This requires that you are
    able to use "sudo" and are using the SDDM session manager...it is
    possible you are using a different session manager).

If all worked successfully, the above steps will restart your graphical
session and return you to the graphical login screen.

See also:
<https://en.wikipedia.org/wiki/Virtual_console>
<https://www.makeuseof.com/what-are-linux-virtual-consoles>

### KDE/Plasma

#### Reloading Plasma

This is a useful tip if you want to restart Plasma without logging out
completely. It's often useful for when you experience some graphical
glitch yet your system is still responsive.

1.  Open KRunner with the "Alt+Space" key combination. A small input box
    (KRunner) should appear towards the top of your screen.
2.  Inside the KRunner input box, enter `plasmashell --replace` and
    press the "Enter" key. This command will restart the Plasma shell
    without logging you out of your session.

#### KRunner

KRunner is the launcher that is built into the Plasma Desktop. It has a
lot of useful features. If you are using KDE/Plasma, this is a great
utility that is worth looking into. You can read more about it here:

<https://userbase.kde.org/Plasma/Krunner/en>