Xcode 4 dropped support for Perforce as an integrated SCM repository. I can live with that, but it also dropped support for user scripts to make it easy to call p4 add/p4 edit on your files. It seems like the best solution to work around this now is to use Automator to create services and then bind those services to hotkeys. So that's what I've done.

To install:

cp -R P4\ Add.workflow ~/Library/Services

cp -R P4\ Edit.workflow ~/Library/Services

In Xcode you should now see P4 Add and P4 Edit under Xcode -> Services. Further, you can select Services -> Services Preferences to bind these commands to a hotkey (I chose ⌘-⇧-A for add and ⌘-⇧-E for edit)

These services will walk up the directory tree from the currently open file in Xcode and look for a .P4CONFIG file with your P4PORT, P4USER and P4CLIENT. I haven't tested extensively, but hopefully in the worst case scenario they'll just fail when they can't find a .P4CONFIG rather than going into an endless loop ;).

One caveat, right now the services are using the last open file in Xcode, which means if you have the Assistant view visible, the file in the right-most pane is the one it acts upon, that's probably not what you'd expect, but that's what it does for now ;).