# ImmortalWrt AX3000T cloud build

Target: Xiaomi Mi Router AX3000T, ordinary/stock layout
Source ref: `v25.12.2`
Target: `mediatek/filogic`
Required kernel options:
- `CONFIG_ZRAM=m`
- `CONFIG_ZRAM_BACKEND_LZO=y`
- `CONFIG_ZRAM_BACKEND_ZSTD=y`

## Run

1. Upload these files to the root of the private GitHub repository.
2. Open **Actions**.
3. Select **Build ImmortalWrt AX3000T (ZRAM ZSTD)**.
4. Click **Run workflow**.
5. Do not flash the artifact until the kernel config and image profile have been checked.

This initial workflow includes LuCI, OpenClash, `kmod-zram`, `zram-swap`, and the Zstandard library package. It intentionally does not embed subscription YAML, Mihomo binaries, node credentials, or private router backups.

The workflow must fail if the generated kernel configuration does not contain all three required ZRAM options or if it cannot find the ordinary AX3000T sysupgrade image.
