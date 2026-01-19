### freedesktop-sdk-25.08.0

Noteworthy changes since 24.08:

* [BREAKING CHANGE] openh264 and ffmpeg-full extensions have been replaced by codecs-extra runtime extension
* [BREAKING CHANGE] intel-vaapi-driver has been removed (replacement is intel-media-driver)
* [BREAKING CHANGE] Dropped elements from Flatpak SDK/Runtime: vulkan-validation-layers, ruby, tcl, tk, libfdk-aac, gtk-doc, pygobject, python-six
* [BREAKING CHANGE] Dropped elements from project: shellingham, requests-toolbelt, pyexpect, html5lib, clikit, cleo, cachecontrol, cachy, sdl2-(image,ttf)
* [BREAKING CHANGE] Perl modules now use major.minor versioned directories and no longer uses the patch version. PERL5LIB or PERLLIB variables may need to be updated.
* [BREAKING CHANGE] gettext: >=0.24 changed location of m4 files. They are now in /usr/share/gettext/m4 Configure scripts etc. needs to updated but this path can also be passed to autoreconf -I /path/to/m4
* [BREAKING CHANGE] automake/autoconf-archive: newer versions perform stricter verifications of flags etc.
* [BREAKING CHANGE] glibc: 2.42 dropped the deprecated and obsolete termio.h header. Anything using it should probably change to termios.h or drop it.
 
