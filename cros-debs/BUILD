# Copyright 2019 The ChromiumOS Authors
# Use of this source code is governed by a BSD-style license that can be
# found in the LICENSE file.

load(":copy_debs.bzl", "copy_debs_to_folder")

# Packages which are the same across different Debian versions.
filegroup(
    name = "cros-debs-common",
    srcs = [
        "//baguette-motd:deb",
        "//cros-adapta:deb",
        "//cros-host-fonts:deb",
        "//cros-logging:deb",
        "//cros-motd:deb",
        "//cros-notificationd:deb",
        "//cros-pipe-config:deb",
        "//cros-port-listener:deb",
        "//cros-sftp:deb",
        "//cros-sommelier:deb",
        "//cros-sommelier-config:deb",
        "//cros-sudo-config:deb",
        "//cros-systemd-overrides:deb",
        "//cros-tast-tests:deb",
        "//cros-ui-config:deb",
        "//cros-vmstat-metrics:deb",
        "//cros-wayland:deb",
        "//cros-xdg-desktop-portal:deb",
    ],
)

filegroup(
    name = "trixie-files",
    srcs = [
        ":cros-debs-common",
        "//cros-apt-config:deb-bookworm",
        "//cros-garcon:deb-bookworm",
        "//cros-guest-tools:deb-bookworm",
    ],
)

filegroup(
    name = "bookworm-files",
    srcs = [
        ":cros-debs-common",
        "//cros-apt-config:deb-bookworm",
        "//cros-garcon:deb-bookworm",
        "//cros-guest-tools:deb-bookworm",
        "//cros-pulse-config:deb",
    ],
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
        ":trixie-debs",
    ],
)
