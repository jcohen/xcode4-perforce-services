Xcode 4 dropped support for Perforce as an integrated SCM repository. I can live with that, but it also dropped support for user scripts to make it easy to call p4 add/p4 edit on your files. It seems like the best solution to work around this now is to use Automator to create services and then bind those services to hotkeys. So that's what I've done.

To install:
cp -R P4\ Add.workflow ~/Library/Services
cp -R P4\ Edit.workflow ~/Library/Services

In Xcode you should now see P4 Add and P4 Edit under Xcode -> Services. Further, you can select Services -> Services Preferences to bind these commands to a hotkey (I chose ⌘-⇧-A for add and ⌘-⇧-E for edit)