# GNOME Runtime Major Changes

## GNOME 50 (alpha)

**gst-thumbnailer**

[gst-thumbnailer](https://gitlab.gnome.org/GNOME/gnome-build-meta/-/blob/master/elements/core/gst-thumbnailers.bst) 
(provides two binaries that create thumbnails for the libgnome-desktop thumbnailer. 
_gst-video-thumbnailer/gst-audio-thumbnailer_ extracts the stored cover art from video/audio files) 
is now part of the GNOME runtime starting with version 50.

## GNOME 49

GNOME runtime inherits the 
[Freedesktop 25.08 components](https://gitlab.com/freedesktop-sdk/freedesktop-sdk/-/tree/release/25.08/elements/components?ref_type=heads) 
and provides 
[GNOME 49 SDK components](https://gitlab.gnome.org/GNOME/gnome-build-meta/-/tree/gnome-49/elements/sdk?ref_type=heads), 
which contain extra modules or an updated version of inherited modules.

### Added

**blueprint-compiler**

[blueprint-compiler](https://gitlab.gnome.org/GNOME/gnome-build-meta/-/blob/gnome-49/elements/sdk/blueprint-compiler.bst) (Blueprint is a markup language and compiler for GTK 4 user interfaces) has been included in the GNOME runtime since version 49. In most cases, you don't need to build this module separately, unless your project requires a specific version or a custom configuration.

**gdk-pixbuf**

([gdk-pixbuf](https://gitlab.gnome.org/GNOME/gnome-build-meta/-/blob/gnome-49/elements/sdk/gdk-pixbuf.bst?ref_type=heads)) (Image loading library) started to use [libglycin/glycin](https://gitlab.gnome.org/GNOME/glycin/-/tree/2.0?ref_type=heads) loader. 

**webp-pixbuf-loader** gdk-pixbuf now supports webp files via the glycin loader. It is no longer necessary to compile the _webp-pixbuf-loader_ module. For other supported formats, see: [libglycin/glycin](https://gitlab.gnome.org/GNOME/glycin/-/tree/2.0?ref_type=heads). 

### Updated

**libmanette-0-2**

Starting with GNOME runtime version 49, _libmanette-0-2_ replaced _libmanette-0-1_ (a simple GObject game controller library).
