# freedesktop-sdk-25.08

[BREAKING CHANGES]

- openh264 and ffmpeg-full extensions have been replaced by codecs-extra runtime extension

- **intel-vaapi-driver** has been removed (replacement is intel-media-driver)

- Perl modules now use major.minor versioned directories and no longer uses the patch version. PERL5LIB or PERLLIB variables may need to be updated.

- gettext: >=0.24 changed location of m4 files. They are now in /usr/share/gettext/m4
  Configure scripts etc. needs to updated but this path can also be passed to autoreconf -I /path/to/m4

- automake/autoconf-archive: newer versions perform stricter verifications of flags etc.

- glibc: 2.42 dropped the deprecated and obsolete termio.h header.
  Anything using it should probably change to termios.h or drop it.

### ADDED

- rr debugger, GNU parallel, skopeo, sdl3, sdl3-(image,ttf), sdl2-compat, fmt, **libtree**, **libsecret**, **taglib**, pahole, nlohmann-json

- **libx264**, **libx265** and **nvenc** support to codecs-extra extension

- **libusb**

- libcamera (not sure) (https://github.com/search?q=org%3Aflathub%20libcamera&type=code)


### DROPPED

- vulkan-validation-layers, ruby, tcl, tk, libfdk-aac, gtk-doc, pygobject, python-six

- shellingham, requests-toolbelt, pyexpect, html5lib, clikit, cleo, cachecontrol, cachy, sdl2-(image,ttf)

### ALREADY ADDED

- libnotify

# freedesktop-sdk-24.08

### ADDED

- libnotify [vendor: gnome, version: 0.8.6](https://github.com/search?q=org%3Aflathub+libnotify&type=code)

