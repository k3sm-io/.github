# k3sm

k3sm is a macOS-native Kubernetes distribution for Apple Silicon — the macOS/arm64 analog of
[k3s](https://github.com/k3s-io/k3s). Pods run as native Darwin processes: real arm64 Mach-O
executables, Seatbelt-confined, on the same Mac as the control plane, which embeds the standard
Kubernetes apiserver, scheduler and controller-manager. There is no Linux, no container runtime,
and no VM in the default path. A Linux `arm64` container image can run too, opt-in, in a per-pod
Virtualization.framework micro-VM through the `vm` RuntimeClass (`runtimeClassName: vm`) —
single-node, `linux/arm64` only, not the default.

## repositories

| Repo | What it does |
|---|---|
| [k3sm](https://github.com/k3sm-io/k3sm) | The distribution — CLI, Virtual Kubelet node, embedded control plane |
| [runtimed](https://github.com/k3sm-io/runtimed) | Native runtime daemon — Seatbelt confinement, APFS image layers, process supervision |
| [darwin-net](https://github.com/k3sm-io/darwin-net) | Pod networking — loopback IP-per-pod, Service proxy, wireguard mesh |
| [apis](https://github.com/k3sm-io/apis) | Shared gRPC, CRD and Go contracts |
| [linux-guest](https://github.com/k3sm-io/linux-guest) | Pinned guest kernel and initramfs releases for the `vm` RuntimeClass |

## status

Pre-1.0. Pre-releases only, on the [k3sm releases page](https://github.com/k3sm-io/k3sm/releases); no
stable release line yet, and no compatibility promise between pre-releases. One maintainer.

## where to start

- [Quickstart](https://github.com/k3sm-io/k3sm/blob/main/docs/user/quickstart.md) — install and
  run a first Pod.
- [Limitations](https://github.com/k3sm-io/k3sm/blob/main/docs/user/limitations.md) — what
  diverges from a Linux cluster, and why.
- [Contributing](https://github.com/k3sm-io/k3sm/blob/main/CONTRIBUTING.md),
  [governance](https://github.com/k3sm-io/k3sm/blob/main/GOVERNANCE.md), and
  [security reporting](https://github.com/k3sm-io/k3sm/blob/main/SECURITY.md).

## support

Sponsor the project: <https://github.com/sponsors/kitsumiko>

Ask questions or discuss ideas: <https://github.com/k3sm-io/k3sm/discussions>

## license

Apache-2.0. Copyright The k3sm Authors. See [LICENSE](LICENSE).
