# GNOME Runtime Major Changes

## GNOME 49

GNOME runtime inherits the Freedesktop runtime version 25.08 (See: [Freedesktop SDK components](https://gitlab.com/freedesktop-sdk/freedesktop-sdk/-/tree/release/25.08/elements/components?ref_type=heads)) and provides some extra modules or an updated version of related modules. (See: [GNOME 49 SDK](https://gitlab.gnome.org/GNOME/gnome-build-meta/-/tree/gnome-49/elements/sdk?ref_type=heads)).

### Added

**blueprint-compiler**

_blueprint-compiler_ (Blueprint is a markup language and compiler for GTK 4 user interfaces) is part of the GNOME runtime starting with version 49. It is no longer necessary to compile, unless the project requires a specific version of this dependency or configuration. See: ([blueprint-compiler.bst](https://gitlab.gnome.org/GNOME/gnome-build-meta/-/blob/gnome-49/elements/sdk/blueprint-compiler.bst)).

**gdk-pixbuf**

_gdk-pixbuf_ (Image loading library) started to use libglycin/glycin loader. ([gdk-pixbuf.bst](https://gitlab.gnome.org/GNOME/gnome-build-meta/-/blob/gnome-49/elements/sdk/gdk-pixbuf.bst?ref_type=heads)).

**webp-pixbuf-loader** gdk-pixbuf now supports webp files via the glycin loader. It is no longer necessary to compile the _webp-pixbuf-loader_ module. For other supported formats, see: ([glycin](https://gitlab.gnome.org/GNOME/glycin/-/tree/2.0?ref_type=heads)).

### Dropped

**libmanette**
