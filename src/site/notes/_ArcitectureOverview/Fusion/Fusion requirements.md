---
{"dg-publish":true,"permalink":"/arcitecture-overview/fusion/fusion-requirements/","tags":["Architecture","Info","Fusion"],"dg-note-properties":{"tags":["Architecture","Info","Fusion"]}}
---

[[_Assets/Photon Fusion 2\|Photon Fusion 2]]

# Fusion requirements

## SDK
- Fusion 2 AppId в Photon Dashboard.
- Fusion SDK 2.x package.
- Unity:
  - `2021.3.45`
  - `2022.3.x`
  - `6.0.x`
- `Project Settings > Editor > Asset Serialization`
  - `Mode = Force Text`

## Supported platforms
- Windows 10 / 11
- macOS / iOS / visionOS
- Android
- WebGL
- PlayStation 4 / 5
- Xbox One / Series X|S
- Nintendo Switch / Switch 2

## Project setup
- `PhotonAppSettings.asset`
  - AppId
  - region settings
- `NetworkProjectConfig.fusion`
  - tick rate
  - prefab/object table
  - simulation settings
- Prefabs с `NetworkObject` должны быть в Object Table.
- После SDK update не затирать:
  - `Photon/Fusion/Resources/NetworkProjectConfig.fusion`
  - `Photon/Fusion/Resources/PhotonAppSettings.asset`

## Runtime minimum
- В сцене/коде должен быть `NetworkRunner`.
- Runner запускается через `StartGame(StartGameArgs)`.
- Один `NetworkRunner` используется только для одной session.
- После shutdown/disconnect — создать новый runner.

## Docs
- [SDK & Download](https://doc.photonengine.com/fusion/current/getting-started/sdk-download)
- [Network Project Config](https://doc.photonengine.com/fusion/current/manual/network-project-config)
