<p align="center">
  <img src="https://raw.githubusercontent.com/overpressure/overpressure/main/docs/logo/overpressure.svg" width="96" height="96" alt="overpressure">
</p>

<h3 align="center">overpressure</h3>
<p align="center">Linux and a SteamOS-compatible userspace for standalone VR headsets, on Valve's Steam Frame kernel.</p>

| Repository | What it holds |
| --- | --- |
| [overpressure](https://github.com/overpressure/overpressure) | The installer and the host tooling, which download each headset's release. Start here. |
| [phoenix](https://github.com/overpressure/phoenix) | The PICO 4: its images, tooling and releases, one headset module. |
| [packages](https://github.com/overpressure/packages) | The Arch packages of the headsets' system, in layers, and each headset's image definition. |
| [linux](https://github.com/overpressure/linux) | Valve's Steam Frame kernel with the project's changes, one branch per layer and headset. |
| [builder](https://github.com/overpressure/builder) | The build image every build runs in, pinned by digest. |

Supported: PICO 4 (Snapdragon XR2). Issues of a headset go to its repository
([overpressure/phoenix](https://github.com/overpressure/phoenix/issues/new/choose)); the installer's, feature
requests and new headsets to [overpressure/overpressure](https://github.com/overpressure/overpressure/issues/new/choose).
