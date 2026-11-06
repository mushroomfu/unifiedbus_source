# Userspace / 用户态

Snapshot of openEuler UnifiedBus (UB) userspace modules, classified by module.
Copied verbatim (minus `.git`); no code or license rewrites.

按模块分类存放的 openEuler 灵衢（UB）用户态源码快照；原样拷贝（不含 `.git`），未改代码与许可证文本。

## Source remotes / 上游来源

Primary hosts `atomgit.com` / `gitcode.com` returned HTTP 418 from this environment.
Clones used the public GitHub read-only mirrors under `openeuler-mirror` (default branch `master`).

本环境访问 atomgit/gitcode 返回 418，故改用 GitHub `openeuler-mirror` 只读镜像（默认分支 `master`）。

| Module | Path | Upstream project | Mirror clone URL | Commit | Commit date (UTC+8) |
|---|---|---|---|---|---|
| UBUS | `userspace/ubus/` | [ubutils](https://atomgit.com/openeuler/ubutils) | https://github.com/openeuler-mirror/ubutils.git | `e7933386e711304accb3912a5614e0565ca58013` | 2026-10-20 14:18:37 |
| UBASE | `userspace/ubase/` | [ubctl](https://atomgit.com/openeuler/ubctl) | https://github.com/openeuler-mirror/ubctl.git | `c29acad711fe54fae5b696600b98cbc2965ceaf5` | 2026-10-30 15:11:25 |
| UMMU | `userspace/ummu/` | [libummu](https://atomgit.com/openeuler/libummu) | https://github.com/openeuler-mirror/libummu.git | `1586fd035d292e3d47dfc3a80987b9fed12eef57` | 2026-09-20 16:08:48 |
| URMA | `userspace/urma/` | [umdk](https://atomgit.com/openeuler/umdk) `src/urma/` | https://github.com/openeuler-mirror/umdk.git | `32a1386b72b3b4a890c89d397f7f6d510564b7a9` | 2026-11-03 17:15:58 |
| URPC | `userspace/urpc/` | umdk `src/urpc/` | same umdk mirror | same umdk commit | same |
| ULOCK | `userspace/ulock/` | umdk `src/ulock/` | same umdk mirror | same umdk commit | same |
| USOCK | `userspace/usock/` | umdk `src/usock/` | same umdk mirror | same umdk commit | same |
| CAM | `userspace/cam/` | umdk `src/cam/` | same umdk mirror | same umdk commit | same |

Mapping notes / 目录对应：

- `ubutils` → `ubus/`（整仓）
- `ubctl` → `ubase/`（整仓）
- `libummu` → `ummu/`（整仓）
- `umdk/src/{urma,urpc,ulock,usock,cam}` → 同名子目录（仅模块树，不含 umdk 顶层 build/doc/test）

## Licenses / 许可证

Do not invent licenses; keep SPDX headers in each file.

- **ubutils / ubctl / libummu**: each tree includes its own `LICENSE` (MIT per upstream file).
- **umdk-derived modules** (`urma`, `urpc`, `ulock`, `usock`, `cam`): see upstream
  [`LICENSES/`](https://github.com/openeuler-mirror/umdk/tree/master/LICENSES)
  — core libraries MIT; files under `src/usock/ums/kmod` are GPL-2.0 kernel code
  (per `LICENSES/README` in umdk). SPDX identifiers remain in individual source files.

Top-level umdk docs (`README.md`, `README_zh.md`, `LICENSES/`) were not copied into each
module directory; consult the umdk mirror linked above.

## Layout / 布局

```
userspace/
  README.md
  ubus/     # from ubutils
  ubase/    # from ubctl
  ummu/     # from libummu
  urma/     # from umdk/src/urma
  urpc/     # from umdk/src/urpc
  ulock/    # from umdk/src/ulock
  usock/    # from umdk/src/usock
  cam/      # from umdk/src/cam
```

This tree is for reading/reference. Standalone build may need umdk top-level CMake,
packaging files, and system dependencies from the original repos.
