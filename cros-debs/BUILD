# Copyright 2019 The ChromiumOS Authors
# Use of this source code is governed by a BSD-style license that can be
# found in the LICENSE file.

load(":copy_debs.bzl", "copy_debs_to_folder")

# Packages which are the same across different Debian versions.
filegroup(
    name = "cros-debs-common",
    srcs = [
        "//baguette-motd:deb",
        "//cros-host-fonts:deb",
        "//cros-logging:deb",
        "//cros-motd:deb",
        "//cros-notificationd:deb",
        "//cros-pipe-config:deb",
        "//cros-port-listener:deb",
        "//cros-sommelier:deb",
        "//cros-sommelier-config:deb",
        "//cros-sudo-config:deb",
        "//cros-systemd-overrides:deb",
        "//cros-tast-tests:deb",
        "//cros-ui-config:deb",
        "//cros-vmstat-metrics:deb",
        "//cros-wayland:deb",
    ],
)

filegroup(
    name = "forky-files",
    srcs = [
        ":cros-debs-common",
        "//cros-adapta:deb-forky",
        "//cros-apt-config:deb-bookworm",
        "//cros-garcon:deb-bookworm",
        "//cros-guest-tools:deb-forky",
    ],
)

filegroup(
    name = "trixie-files",
    srcs = [
        ":cros-debs-common",
        "//cros-adapta:deb",
        "//cros-apt-config:deb-bookworm",
        "//cros-garcon:deb-bookworm",
        "//cros-guest-tools:deb-bookworm",
        "//cros-sftp:deb",
        "//cros-xdg-desktop-portal:deb",
    ],
)

filegroup(
    name = "bookworm-files",
    srcs = [
        ":cros-debs-common",
        "//cros-adapta:deb",
        "//cros-apt-config:deb-bookworm",
        "//cros-garcon:deb-bookworm",
        "//cros-guest-tools:deb-bookworm",
        "//cros-pulse-config:deb",
        "//cros-sftp:deb",
        "//cros-xdg-desktop-portal:deb",
    ],
)

copy_debs_to_folder(
    name = "forky-debs",
    srcs = [":forky-files"],
    out_dir = "forky-debs",
)

copy_debs_to_folder(
    name = "trixie-debs",
    srcs = [":trixie-files"],
    out_dir = "trixie-debs",
)

copy_debs_to_folder(
    name = "bookworm-debs",
    srcs = [":bookworm-files"],
    out_dir = "bookworm-debs",
)

filegroup(
    name = "debs",
    srcs = [
        ":bookworm-debs",
        ":forky-debs",
        ":trixie-debs",
    ],
)
