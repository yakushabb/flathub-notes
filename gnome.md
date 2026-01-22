# GNOME Runtime Major Changes

## GNOME 49

### Added

**blueprint-compiler**

_blueprint-compiler_ (Blueprint is a markup language and compiler for GTK 4 user interfaces) is part of the GNOME runtime starting with version 49. It is no longer necessary to compile, unless the project requires a specific version of this dependency or configuration.

**gdk-pixbuf**

_gdk-pixbuf_ (Image loading library) no longer relies on x instead of using libglycin/glaycin loader. ([*](https://gitlab.gnome.org/GNOME/gnome-build-meta/-/blob/gnome-49/elements/sdk/gdk-pixbuf.bst?ref_type=heads))

### Dropped

**libmanette**
