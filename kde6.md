# KDE Runtime Major Changes

## 6.10

KDE runtime inherits the 
[Freedesktop 25.08 components](https://gitlab.com/freedesktop-sdk/freedesktop-sdk/-/tree/release/25.08/elements/components?ref_type=heads) 
and provides 
[KDE runtime 6.10 components](https://invent.kde.org/packaging/flatpak-kde-runtime/-/blob/qt6.10/org.kde.Sdk.json.in?ref_type=heads), 
which contain extra modules or an updated version of inherited modules.

### Added

### Updated

## 6.9

KDE runtime inherits the 
[Freedesktop 24.08 components](https://gitlab.com/freedesktop-sdk/freedesktop-sdk/-/tree/release/24.08/elements/components?ref_type=heads) 
and provides 
[KDE runtime 6.9 components](https://invent.kde.org/packaging/flatpak-kde-runtime/-/blob/qt6.9/org.kde.Sdk.json.in?ref_type=heads), 
which contain extra modules or an updated version of inherited modules.

**module name**

### Added

**kirigami addons**

_kirigami-addons_ (Add-ons for the Kirigami framework) has been included in the KDE runtime since version 6.9. In most cases, you don't need to build this module separately, unless your project requires a specific version or a custom configuration.

**ocean sound theme** 

_ocean-sound-theme_ (Ocean Sound Theme for Plasma) has been included in the KDE runtime since version 6.9. In most cases, you don't need to build this module separately, unless your project requires a specific version or a custom configuration.

## 6.8

KDE runtime inherits the 
[Freedesktop 24.08 components](https://gitlab.com/freedesktop-sdk/freedesktop-sdk/-/tree/release/24.08/elements/components?ref_type=heads) 
and provides 
[KDE runtime 6.8 components](https://invent.kde.org/packaging/flatpak-kde-runtime/-/blob/qt6.8/org.kde.Sdk.json.in?ref_type=heads), 
which contain extra modules or an updated version of inherited modules.

### Dropped

**Phonon VLC**

_phonon-vlc_ (VLC backend for the Phonon multimedia library) is no longer included in the KDE runtime as of version 6.8. If your project still depends on it, you’ll need to build this module separately.

