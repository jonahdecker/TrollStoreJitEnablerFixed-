# TrollStoreJitEnabler

You can use Sideloadly, Azule, Esign, or any other dylib/deb injection tools to inject this tweak into your app which supports JIT (Just-In-Time Compilation). 

# Un-Sandboxing
These entitlements are needed to un-Sandbox on iOS 17. You only need to use one of the top 3 entitlements along with the remaining entitlements to disable Sandbox. 
```
<key>com.apple.private.security.container-required</key>
<false/>
```
```
<key>com.apple.private.security.no-container</key>
<true/>
```
```
<key>com.apple.private.security.no-sandbox</key>
<true/>
```

```
<key>get-task-allow</key>
<true/>
```
```
<key>platform-application</key>
<true/>
```

```
<key>com.apple.private.security.iokit-user-client-class</key>
<array>
  <string>IOSurfaceRootUserClient</string>
  <string>AGXDeviceUserClient</string>
  <string>AGXSharedUserClient</string>
  <string>AGXCommmandQueue</string>
  <string>AGXDevice</string>
</array>
```
# Give ability to change Jetsam task limit by itself 
```
<key>com.apple.private.memorystatus</key>
<true/>
```
# Treat app as system app (if previously installed before under Debian package), which requires this entitlement
```
<key>com.apple.private.memorystatus</key>
<true/>
```
# Keep App Container
ProvaLauncher also used these entitlements with the above. This will allow you to have a Play! folder located in the Files app. 
```
<key>com.apple.private.security.storage.AppDataContainers</key>
<true/>
```
```
<key>com.apple.private.security.storage.MobileDocuments</key>
<true/>
```

# Based on
https://github.com/PojavLauncherTeam/PojavLauncher_iOS/commit/ccaa9416f182dad0bc26832cbec85b799ae47dad#diff-0b345163bfb92b086397dec9b5f5f475cb6610283e8fb5c722763e6fb3d39db0
# TrollStoreJitEnablerFixed-
