# Maintainer: XX11org discor: m1rxx11org (dont ask anything about wayland)
pkgname=legacy-launcher
pkgver=bootstrap
pkgrel=1
pkgdesc="Legacy Launcher ArchLinux"
arch=('any')
url="https://llaun.ch"
license=('custom')
depends=('jdk21-openjdk')
source=('LegacyLauncher.jar::https://dl.llaun.ch/legacy/bootstrap')
sha256sums=('SKIP')

package() {
    install -Dm644 "$srcdir/LegacyLauncher.jar" "$pkgdir/usr/share/legacy-launcher/LegacyLauncher.jar"

    install -dm755 "$pkgdir/usr/bin"
    cat << 'EOF' > "$pkgdir/usr/bin/LegacyLauncher"
#!/bin/sh
exec java -jar /usr/share/legacy-launcher/LegacyLauncher.jar "$@"
EOF
    chmod +x "$pkgdir/usr/bin/LegacyLauncher"

    install -dm755 "$pkgdir/usr/share/applications"
    cat << 'EOF' > "$pkgdir/usr/share/applications/LegacyLauncher.desktop"
[Desktop Entry]
Type=Application
Name=Legacy Launcher
Comment=Minecraft Legacy Launcher
Exec=LegacyLauncher
Icon=utilities-terminal
Terminal=false
Categories=Game;
EOF
}
