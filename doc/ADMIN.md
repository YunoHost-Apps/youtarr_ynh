## First login

Log in with the YunoHost user/password you provided during install. From there, change your password from Youtarr's own settings if you want it to differ from the one used to seed the account — it's independent of your YunoHost credentials and won't be reset on upgrades or restarts.

## Storing downloads on external storage (e.g. a media server library)

By default Youtarr stores downloaded videos in its own data directory. To point it at another location instead (a NAS mount, another app's media library...), go to the app's config panel ("Storage" > "Download location") and set the desired path.

Before doing so, make sure the `youtarr` system user can actually read/write that path — for example, if the target directory is owned by a group (like a shared `multimedia` group used by other media apps on your server), add `youtarr` to that group:

```
usermod -aG multimedia youtarr
systemctl restart youtarr
```

Without this, Youtarr will fail to write downloaded files even though the path is configured correctly.
