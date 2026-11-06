# unifiedbus_source

Snapshot of openEuler UnifiedBus (UB) related **kernel** and **userspace** modules,
copied verbatim with module-oriented layout. No code or license changes.

openEuler 灵衢（UB）相关**内核**与**用户态**模块快照；按模块整理存放，未改代码与许可证。

---

## Kernel / 内核

- Source: openEuler kernel, branch `OLK-6.6`
  (mirror https://github.com/openeuler-mirror/kernel of https://atomgit.com/openeuler/kernel)
- Source commit: `951c1479eef3b4cafc50dc03c7e1b56127f237d7` (2026-11-05 16:30:22 +0800)
- License: see `COPYING` and the SPDX headers in each file (GPL-2.0 kernel code).

| Module | Paths |
|---|---|
| UBUS | `drivers/ub/ubus/`, `include/ub/ubus/` |
| UBFI | `drivers/ub/ubfi/`, `include/ub/ubfi/` |
| UBASE | `drivers/ub/ubase/`, `include/ub/ubase/` |
| UBASEPROXY | `drivers/ub/ubaseproxy/` |
| UMMU | `drivers/iommu/hisilicon/` (incl. `ummu-core/`, `logic_ummu/`, `ubmem-mmu/`) |
| CDMA | `drivers/ub/cdma/`, `include/ub/cdma/` |
| UNIC / UBL | `drivers/net/ub/` (`unic/`, `dev/`, Kconfig, Makefile) |
| UBDEVSHM | `drivers/ub/ubdevshm/`, `include/ub/ubdevshm/` |
| UBMEMPFD | `drivers/ub/ubmempfd/` |
| UDMA | `drivers/ub/urma/hw/udma/`, `include/ub/urma/udma/` |

Parent Kconfig/Makefile files (e.g. `drivers/ub/Kconfig`) are not included,
so this tree is for reading/reference and does not build standalone.

---

## Userspace / 用户态

See [`userspace/README.md`](userspace/README.md) for full upstream URLs and SHAs.

Cloned from GitHub `openeuler-mirror` (atomgit/gitcode returned HTTP 418 here).

| Module | Path | Upstream | Commit |
|---|---|---|---|
| UBUS | `userspace/ubus/` | ubutils | `e7933386e711304accb3912a5614e0565ca58013` |
| UBASE | `userspace/ubase/` | ubctl | `c29acad711fe54fae5b696600b98cbc2965ceaf5` |
| UMMU | `userspace/ummu/` | libummu | `1586fd035d292e3d47dfc3a80987b9fed12eef57` |
| URMA | `userspace/urma/` | umdk `src/urma/` | `32a1386b72b3b4a890c89d397f7f6d510564b7a9` |
| URPC | `userspace/urpc/` | umdk `src/urpc/` | (same umdk commit) |
| ULOCK | `userspace/ulock/` | umdk `src/ulock/` | (same umdk commit) |
| USOCK | `userspace/usock/` | umdk `src/usock/` | (same umdk commit) |
| CAM | `userspace/cam/` | umdk `src/cam/` | (same umdk commit) |

Licenses: per-tree `LICENSE` for ubutils/ubctl/libummu (MIT upstream text);
umdk modules follow umdk `LICENSES/` (MIT core; GPL-2.0 for `usock` kmod) — see userspace README.
