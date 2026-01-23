# Freedesktop Runtime Major Changes

## Freedesktop 25.08 

GNOME 49, KDE runtime 6.10 and 5.15-28.0 inherit Freedesktop components.  

- [Freedesktop SDK components](https://gitlab.com/freedesktop-sdk/freedesktop-sdk/-/tree/release/25.08/elements/components?ref_type=heads)

### Added

**openh264 and ffmpeg-full extensions**

_openh264_ and _ffmpeg-full_ extensions have been replaced by _codecs-extra_ runtime extension. App developers or maintainers will no longer need to add the snippet below to get h.264/h.265 working. It is supposed to be automatically handled by the runtime. ([*](https://gitlab.gnome.org/GNOME/gnome-build-meta/-/issues/931))

```
add-extensions:
  org.freedesktop.Platform.ffmpeg-full:
    version: '24.08'
    directory: lib/ffmpeg
    add-ld-path: .
```

**GStreamer**

Additionally GST_PLUGIN_SYSTEM_PATH environment variable needs to be updated to include: `%{libdir}/codecs-extra/lib/gstreamer-1.0`. ([*](https://gitlab.gnome.org/GNOME/gnome-build-meta/-/issues/931#note_2350019))

```
GST_PLUGIN_SYSTEM_PATH: /app/lib/gstreamer-1.0:/usr/lib/extensions/gstreamer-1.0:%{libdir}/codecs-extra/lib/gstreamer-1.0:%{libdir}/gstreamer-1.0
```

**SDL3**

Freedesktop runtime **25.08** and related runtimes provide several SDL modules that might be useful to drop from the build manifest.

- [sdl3](https://gitlab.com/freedesktop-sdk/freedesktop-sdk/-/blob/release/25.08/elements/components/sdl3.bst)
- [sdl3-image](https://gitlab.com/freedesktop-sdk/freedesktop-sdk/-/blob/release/25.08/elements/components/sdl3-image.bst)
- [sdl3-ttf](https://gitlab.com/freedesktop-sdk/freedesktop-sdk/-/blob/release/25.08/elements/components/sdl3-ttf.bst)
- [sdl2-compat](https://gitlab.com/freedesktop-sdk/freedesktop-sdk/-/blob/release/25.08/elements/components/sdl2-compat.bst)
- [sdl2-mixer](https://gitlab.com/freedesktop-sdk/freedesktop-sdk/-/blob/release/25.08/elements/components/sdl2-mixer.bst)
- [sdl2-net](https://gitlab.com/freedesktop-sdk/freedesktop-sdk/-/blob/release/25.08/elements/components/sdl2-net.bst)

**intel-vaapi-driver** has been removed (replacement is intel-media-driver)

Perl modules now use major.minor versioned directories and no longer uses the patch version. PERL5LIB or PERLLIB variables may need to be updated.

gettext: >=0.24 changed location of m4 files. They are now in /usr/share/gettext/m4
  Configure scripts etc. needs to updated but this path can also be passed to autoreconf -I /path/to/m4

automake/autoconf-archive: newer versions perform stricter verifications of flags etc.

glibc: 2.42 dropped the deprecated and obsolete termio.h header.
  Anything using it should probably change to termios.h or drop it.

- _rr debugger_, _GNU parallel_, _skopeo_, _sdl3_, _sdl3-(image,ttf)_, _sdl2-compat_, _fmtlib/fmt_, _libtree_, _libsecret_, _taglib_, _pahole_

- libx264, libx265 and nvenc support to codecs-extra extension

- _libusb_

### DROPPED

- vulkan-validation-layers, ruby, tcl, tk, libfdk-aac, gtk-doc, pygobject, python-six

- shellingham, requests-toolbelt, pyexpect, html5lib, clikit, cleo, cachecontrol, cachy, sdl2-(image,ttf)

### TASKS

- [x] libusb [related issues](https://github.com/issues?q=is%3Aissue%20is%3Aopen%20archived%3Afalse%20org%3Aflathub%20libusb)
- [x] libsecret [related issues](https://github.com/issues?q=is%3Aissue%20is%3Aopen%20archived%3Afalse%20org%3Aflathub%20libsecret)
- [x] taglib [related issues](https://github.com/issues?q=is%3Aissue%20is%3Aopen%20archived%3Afalse%20org%3Aflathub%20taglib)
- [x] fmtlib [related issues](https://github.com/issues?q=is%3Aissue%20is%3Aopen%20archived%3Afalse%20org%3Aflathub%20fmtlib)
- [x] FFMPEG and ffmpeg extension [related issues](https://github.com/issues?q=is%3Aissue%20is%3Aopen%20archived%3Afalse%20org%3Aflathub%20ffmpeg)
- [x] SDL [related issues](https://github.com/issues?q=is%3Aissue%20is%3Aopen%20archived%3Afalse%20org%3Aflathub%20sdl)

## Freedesktop 24.08

### ADDED

- libnotify

### TASKS

- [x] libnotify [related issues](https://github.com/issues?q=is%3Aissue%20is%3Aopen%20archived%3Afalse%20org%3Aflathub%20libnotify)

