# unifiedbus_source

Snapshot of openEuler kernel UnifiedBus (UB) related modules, copied verbatim
with the original kernel directory layout. No code or license changes.

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
