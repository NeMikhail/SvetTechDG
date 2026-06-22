---
{"dg-publish":true,"permalink":"/assets/photon-fusion-2/","tags":["Info","Fusion"],"dg-note-properties":{"tags":["Info","Fusion"]}}
---

# Photon Fusion 2

> [!summary] Что это
> High-performance networking SDK для Unity: state sync, prediction, lag compensation, AOI, RPC, matchmaking.

## Главное
- Единица работы: `NetworkRunner` = один сетевой peer.
- Сетевые сущности: `NetworkObject` + `NetworkBehaviour`.
- Состояние: `[Networked]` properties.
- Логика симуляции: `FixedUpdateNetwork()`.
- Визуал/interpolation: `Render()`.
- Время: tick-based simulation, не FPS.

## Режимы
| Mode | Кто authority | Когда брать |
|---|---|---|
| `GameMode.Server` + `Client` | dedicated server | честность, серверный контроль |
| `GameMode.Host` + `Client` | player-host | дешевле, но host trusted |
| `GameMode.Shared` | клиенты делят authority | co-op / PUN-like модель |
| `GameMode.Single` | локально | singleplayer без отдельного кода |

## Базовые понятия
- `State Authority` — кто пишет authoritative state объекта.
- `Input Authority` — чей input управляет объектом.
- `Proxy` — объект без локальной authority.
- Snapshot — состояние объекта на конкретном tick.
- Prediction — локальная симуляция будущего состояния.
- Resimulation — пересчёт после получения authoritative state.

## Связанные заметки
- [[_ArcitectureOverview/Fusion/Fusion requirements\|Fusion requirements]]
- [[_ArcitectureOverview/Fusion/Fusion gameloop\|Fusion gameloop]]

## Docs
- [Fusion 2 Introduction](https://doc.photonengine.com/fusion/current/fusion-2-intro)
- [Network Topologies](https://doc.photonengine.com/fusion/current/manual/network-topologies)
- [Network Runner](https://doc.photonengine.com/fusion/current/manual/network-runner)
