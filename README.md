# CR8809 ImmortalWrt custom builder

Target: Xiaomi CR8809 M79 / IPQ5018, matched to zcop's `redmi_ax3000` device definition (which explicitly lists CR880X M79 as an alternate model).

Base source is pinned to zcop/immortalwrt commit `2db347236cb6fa1ca9fea893d93b1cbc6085e073`, matching the known-working firmware family (Linux 6.12.87, qualcommax/ipq50xx, aarch64).

## Build

1. Open Actions.
2. Select **Build CR8809 ImmortalWrt**.
3. Select **Run workflow** on branch `build/cr8809-custom`.
4. Download the artifact only after the job succeeds.

The workflow pins package and LuCI feeds, builds OpenClash with the ARM64 Mihomo Meta core and AdGuard Home into the image, includes Chinese LuCI translations and nlbwmon, and rejects factory UBI images larger than 36 MiB (37,748,736 bytes).

## Safety

Do not flash unless the workflow completed successfully, the UBI size check passed, and SHA256 has been verified. Keep the original firmware backup and serial recovery access available.

## Package feed status

The workflow uploads generated packages as build artifacts. A persistent signed APK feed / Pages deployment is a separate publishing step and is not claimed to be active yet.
