[🇰🇷 한국어](README.ko.md) | [🇯🇵 日本語](README.ja.md)

# VRM Chat Room

**Multi-avatar 3D chat room with VRM models, WebSocket real-time messaging, floating speech bubbles, and Mixamo animation retargeting.**

> From the [NVatar](https://github.com/nskit-io/nvatar) project — an AI avatar chat system running entirely on local hardware.

---

## Why This Exists

Ready Player Me shut down. The VRM ecosystem lacks a simple, focused demo of what a **3D avatar chat room** looks like on the modern web. Heavy metaverse frameworks exist (VerseEngine, Third Room), but no lightweight implementation ties together:

1. **VRM avatars** rendered with three-vrm
2. **WebSocket** real-time multi-user chat
3. **Speech bubbles** floating above 3D avatar heads
4. **Mixamo FBX** animation retargeting to VRM skeletons

This is that demo.

## Features

### 3D Avatar System
- **VRM 1.0** models via [@pixiv/three-vrm](https://github.com/pixiv/three-vrm) 3.3.3
- **Auto blink**: Randomized natural blink intervals
- **Idle breathing**: Subtle spine and body micro-movements
- **Eye tracking**: Smooth interpolated eye tracking

### Emotion Poses
Blend of VRM expressions + bone rotation:

| Emotion | Body | Expression |
|---------|------|------------|
| Happy | Arms back, spine back | Smile blend shape |
| Sad | Shoulders forward, spine slump, head down | Sad blend shape |
| Angry | Fists clenched, spine back | Angry blend shape |
| Surprised | Arms up, back jolt | Surprised blend shape |

### Mixamo FBX Retargeting
- Load Mixamo FBX → Remove position tracks (rotation only)
- Custom rest-pose correction algorithm for accurate bone mapping
- Position movement handled by JavaScript
- Included motions: Idle, Walking

### Speech Bubble System
- 3D head position → `camera.project()` → 2D screen coordinates
- Bubble queue: Timed display with fade transitions
- Separate DOM elements synced to 3D positions every frame

### Virtual Room
- 3D environment: walls (3 sides), wood floor, window with PointLight, furniture
- DOM overlay: chat panel, emotion buttons, avatar selector
- Double-click movement: raycaster → 3D target → walking animation → idle on arrival

### Double-Click Navigation
- Click on floor → raycaster converts to 3D position
- Avatar walks toward target with walking animation
- Automatically switches to idle on arrival

## Tech Stack

| Component | Technology |
|-----------|-----------|
| 3D Engine | Three.js 0.160 |
| VRM | @pixiv/three-vrm 3.3.3 |
| Animations | Mixamo FBX |
| Rendering | WebGLRenderer |
| UI | DOM Overlay |
| Real-time | WebSocket |

## VRM Model Sources

- [VRoid Hub](https://hub.vroid.com/) — Free VRM models
- [BOOTH](https://booth.pm/) — Indie marketplace
- [CharacterStudio](https://github.com/memelotsqui/CharacterStudio) — Open-source VRM editor

## Two Demo Views

### Avatar Lab (`avatar-demo.html`)
Test VRM models, expressions, and animations in isolation.

### Chat Room (`room-demo.html`)
Full virtual room with avatar + chat integration, furniture, and multi-avatar support.

## Related Projects

Other open-source components from the NVatar AI avatar system:

- [**Try Live Demo**](https://nskit-io.github.io/nvatar-demo/) — Experience NVatar in your browser

- [**avatar-chat**](https://github.com/nskit-io/avatar-chat) — Prompt engineering patterns for Gemma character AI
- [**chat-like-human-memory**](https://github.com/nskit-io/chat-like-human-memory) — 9D emotion tracking + personality evolution + 3-tier memory
- [**customize-local-llm**](https://github.com/nskit-io/customize-local-llm) — Local Gemma for personality, cloud Claude for facts
- [**CSW**](https://github.com/nskit-io/csw) — Claude Subscription Worker powering the cloud layer
- [**portable-ai-companion**](https://github.com/nskit-io/portable-ai-companion) — Cross-app franchise architecture for avatar portability

## License

CC BY-NC-SA 4.0 — see [LICENSE](LICENSE)

---

## Support This Project

NVatar is an independent R&D project exploring the frontier of AI character systems. Built by a solo founder at Neoulsoft Inc. — independent R&D, no external funding yet. Built by a solo founder at Neoulsoft Inc. — independent R&D, no external funding yet.

If you find this work valuable:

**Donation & Investment Inquiry**
- Email: [nskit@nskit.io](mailto:nskit@nskit.io)
- Organization: [NSKit](https://nskit.io) by Neoulsoft Inc.

<p align="center">
  <a href="https://github.com/nskit-io">github.com/nskit-io</a>
</p>
