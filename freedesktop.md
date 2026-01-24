# Freedesktop Runtime Major Changes

## Freedesktop 25.08

GNOME 49, KDE runtime 6.10 and 5.15-28.0 inherit 
[Freedesktop 25.08 components](https://gitlab.com/freedesktop-sdk/freedesktop-sdk/-/tree/release/25.08/elements/components?ref_type=heads).

### Added

**openh264 and ffmpeg-full extensions**

_openh264_ and _ffmpeg-full_ extensions have been replaced by _codecs-extra_ runtime extension. 
App developers or maintainers will no longer need to add the snippet below to get h.264/h.265 working. 
It is supposed to be automatically handled by the runtime. ([*](https://gitlab.gnome.org/GNOME/gnome-build-meta/-/issues/931))

```yaml
add-extensions:
  org.freedesktop.Platform.ffmpeg-full:
    version: '24.08'
    directory: lib/ffmpeg
    add-ld-path: .
```

**GStreamer**

Additionally GST_PLUGIN_SYSTEM_PATH environment variable needs to be updated to 
include: `%{libdir}/codecs-extra/lib/gstreamer-1.0`. ([*](https://gitlab.gnome.org/GNOME/gnome-build-meta/-/issues/931#note_2350019))

```json
"--env=GST_PLUGIN_SYSTEM_PATH=/app/lib/gstreamer-1.0:/usr/lib/extensions/codecs-extra/lib/gstreamer-1.0:/usr/lib/x86_64-linux-gnu/gstreamer-1.0",
```

**libx264, libx265 and nvenc**

codecs-extra extension now supports libx264, libx265 and nvenc extension. 
It is no longer necessary to compile these modules, unless the project requires a specific version or configuration of these dependencies.

**SDL3**

Freedesktop runtime **25.08** and related runtimes provide several SDL3/SDL2 modules. 
It is no longer necessary to compile these modules, unless the project requires a specific version or configuration of these dependencies.

Flathub also provides several [SDL2](https://github.com/flathub/shared-modules/tree/master/SDL2) and [SDL1](https://github.com/flathub/shared-modules/tree/master/SDL) modules via the shared-modules repository.

- [sdl3](https://gitlab.com/freedesktop-sdk/freedesktop-sdk/-/blob/release/25.08/elements/components/sdl3.bst)
- [sdl3-image](https://gitlab.com/freedesktop-sdk/freedesktop-sdk/-/blob/release/25.08/elements/components/sdl3-image.bst)
- [sdl3-ttf](https://gitlab.com/freedesktop-sdk/freedesktop-sdk/-/blob/release/25.08/elements/components/sdl3-ttf.bst)
- [sdl2-compat](https://gitlab.com/freedesktop-sdk/freedesktop-sdk/-/blob/release/25.08/elements/components/sdl2-compat.bst)
- [sdl2-mixer](https://gitlab.com/freedesktop-sdk/freedesktop-sdk/-/blob/release/25.08/elements/components/sdl2-mixer.bst)
- [sdl2-net](https://gitlab.com/freedesktop-sdk/freedesktop-sdk/-/blob/release/25.08/elements/components/sdl2-net.bst)

**libusb**

Freedesktop runtime **25.08** and related runtimes provide 
[libusb/libusb](https://gitlab.com/freedesktop-sdk/freedesktop-sdk/-/blob/release/25.08/elements/components/libusb.bst). 
In most cases, you don't need to build this module separately, unless your project requires a specific version or a custom configuration.

**libsecret**

Freedesktop runtime **25.08** and related runtimes provide 
[gnome/libsecret](https://gitlab.com/freedesktop-sdk/freedesktop-sdk/-/blob/release/25.08/elements/components/libsecret.bst). 
In most cases, you don't need to build this module separately, unless your project requires a specific version or a custom configuration.

**taglib**

Freedesktop runtime **25.08** and related runtimes provide 
[taglib/taglib](https://gitlab.com/freedesktop-sdk/freedesktop-sdk/-/blob/release/25.08/elements/components/taglib.bst). 
In most cases, you don't need to build this module separately, unless your project requires a specific version or a custom configuration.

**fmtlib**

Freedesktop runtime **25.08** and related runtimes provide 
[fmtlib/fmt](https://gitlab.com/freedesktop-sdk/freedesktop-sdk/-/blob/release/25.08/elements/components/fmtlib.bst). 
In most cases, you don't need to build this module separately, unless your project requires a specific version or a custom configuration.

**Other Modules**

- rr debugger
- GNU parallel
- skopeo
- libtree
- pahole

### DROPPED

**sdl2-image and sdl2-ttf**

These modules dropped from Freedesktop runtime version 25.08, hovewer Flathub still provides them via the 
[shared-modules/SDL2](https://github.com/flathub/shared-modules/tree/master/SDL2) repository.

**glibc/termio.h**

glibc: 2.42 dropped the deprecated and obsolete termio.h header. Anything using it should probably change to termios.h or drop it.

**Other Modules**

- cachecontrol
- cachy
- cleo
- clikit
- gtk-doc
- html5lib
- libfdk-aac
- pyexpect
- pygobject
- python-six
- requests-toolbelt
- ruby
- shellingham
- tcl
- tk
- vulkan-validation-layers

### Other Changes

**intel-vaapi-driver**

- _intel-vaapi-driver_ has been removed and replacement is _intel-media-driver_.


**Perl modules**

Perl modules now use major.minor versioned directories and no longer uses the patch version. PERL5LIB or PERLLIB variables may need to be updated.

**gettext**

gettext: >=0.24 changed location of m4 files. They are now in `/usr/share/gettext/m4`. 

Configure scripts etc. needs to updated but this path can also be passed to `autoreconf -I /path/to/m4`

**automake**

automake/autoconf-archive: newer versions perform stricter verifications of flags etc.

### TASKS

- [x] FFMPEG and ffmpeg extension [related issues](https://github.com/issues?q=is%3Aissue%20is%3Aopen%20archived%3Afalse%20org%3Aflathub%20ffmpeg)
- [x] SDL [related issues](https://github.com/issues?q=is%3Aissue%20is%3Aopen%20archived%3Afalse%20org%3Aflathub%20sdl)
- [x] libusb [related issues](https://github.com/issues?q=is%3Aissue%20is%3Aopen%20archived%3Afalse%20org%3Aflathub%20libusb)
- [x] libsecret [related issues](https://github.com/issues?q=is%3Aissue%20is%3Aopen%20archived%3Afalse%20org%3Aflathub%20libsecret)
- [x] taglib [related issues](https://github.com/issues?q=is%3Aissue%20is%3Aopen%20archived%3Afalse%20org%3Aflathub%20taglib)
- [x] fmtlib [related issues](https://github.com/issues?q=is%3Aissue%20is%3Aopen%20archived%3Afalse%20org%3Aflathub%20fmtlib)

---

## Freedesktop 24.08

### ADDED

- libnotify

### TASKS

- [x] libnotify [related issues](https://github.com/issues?q=is%3Aissue%20is%3Aopen%20archived%3Afalse%20org%3Aflathub%20libnotify)

