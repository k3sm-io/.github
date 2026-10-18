# k3sm

k3sm is a macOS-native Kubernetes distribution for Apple Silicon, the macOS/arm64 analog of
[k3s](https://github.com/k3s-io/k3s). Pods run as native Darwin processes: real arm64 Mach-O
executables, isolated with a Seatbelt sandbox, on the same Mac as the control plane, which embeds
the standard Kubernetes apiserver, scheduler and controller-manager. There is no Linux, no
container runtime, and no VM in the default path. A Linux `arm64` container image can run too,
opt-in, in a per-pod Virtualization.framework micro-VM through the `vm` RuntimeClass
(`runtimeClassName: vm`).

## repositories

| Repo | What it does |
|---|---|
| [k3sm](https://github.com/k3sm-io/k3sm) | The distribution: the CLI, the Virtual Kubelet node, the embedded control plane |
| [runtimed](https://github.com/k3sm-io/runtimed) | Native runtime daemon: Seatbelt confinement, APFS image layers, process supervision |
| [darwin-net](https://github.com/k3sm-io/darwin-net) | Pod networking: loopback IP-per-pod, Service proxy, wireguard mesh |
| [apis](https://github.com/k3sm-io/apis) | Shared gRPC, CRD and Go contracts |
| [app](https://github.com/k3sm-io/app) | The macOS app: a menu bar status item, and a window with the cluster, this Mac, the nodes and a workloads console |
| [k3sm-sdk-cpp](https://github.com/k3sm-io/k3sm-sdk-cpp) | A header-only C++ client for the node pressure and headroom API (the API design is in progress) |
| [linux-guest](https://github.com/k3sm-io/linux-guest) | Pinned guest kernel and initramfs releases for the `vm` RuntimeClass |

## status

Pre-1.0. Pre-releases only, on the [k3sm releases page](https://github.com/k3sm-io/k3sm/releases);
the latest is v0.1.7, of 2026-10-05. There is no stable release line yet, and no compatibility
promise between pre-releases. One maintainer. Multi-node clusters are a preview across two Macs;
they graduate in a later release.

## where to start

- [Quickstart](https://github.com/k3sm-io/k3sm/blob/main/docs/user/quickstart.md): install and
  run a first Pod.
- [Limitations](https://github.com/k3sm-io/k3sm/blob/main/docs/user/limitations.md): what
  differs from a Linux cluster, and why.
- [Contributing](https://github.com/k3sm-io/k3sm/blob/main/CONTRIBUTING.md),
  [governance](https://github.com/k3sm-io/k3sm/blob/main/GOVERNANCE.md), and
  [security reporting](https://github.com/k3sm-io/k3sm/blob/main/SECURITY.md).

## support

Sponsor the project: <https://github.com/sponsors/kitsumiko>

Ask questions or discuss ideas: <https://github.com/k3sm-io/k3sm/discussions>

## license

Apache-2.0. Copyright The k3sm Authors. See the
[LICENSE](https://github.com/k3sm-io/k3sm/blob/main/LICENSE).
