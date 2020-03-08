# macOS Specific

App is damaged and can't be opened. You should move it to the trash.

```bash
sudo xattr -rd com.apple.quarantine /Applications/Some.app
```

Launch Boot Utility OR Reinstall MAC etc

```bash
CMD + R > Press POWER Buttun
```

When BOOTing you see cross sign -> press CMD+R+ POWER button > Repair disk will solve problem


### Enable at command

```bash
launchctl load -w /System/Library/LaunchDaemons/com.apple.atrun.plist
```

```shell script
killall -KILL SystemUIServer
```
