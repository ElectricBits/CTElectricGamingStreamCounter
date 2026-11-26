# Domain Checklists

Use during decomposition (Phase 2) and the "sounds achievable, likely disappoints" check (Phase 4). Pick the domains that apply; most projects touch several.

## Universal hidden requirements
Often forgotten, often expensive:
- Save/load, persistence, data migration between versions
- Settings, input remapping, accessibility (text size, colour-blind modes, captions, controller support)
- Error handling, offline behaviour, reconnection
- Authentication, accounts, security of secrets/API keys (never ship keys in a client)
- Logging, crash reporting, analytics (and consent/privacy)
- Build, packaging, code signing, installer, auto-update
- Store/platform submission rules and review times
- Licences of code, assets, fonts, music; third-party API terms
- Localisation
- Testing on real target hardware; QA time
- Content production (art, audio, levels, text) - frequently larger than the code

## Games
**Systems:** core loop, input, camera, physics/collision, character controller, animation, AI/NPC behaviour, level design & tools, UI/HUD/menus, audio, save system, progression/economy, rendering & VFX, performance/LOD, networking (if multiplayer), platform services (achievements, cloud saves), tutorials/onboarding.

**Sounds easy, often disappoints:**
- **Physics-based movement** (swinging, grappling, ragdolls, vehicles, climbing): getting it *working* is quick; making it *feel good* is weeks of tuning, custom constraints and frequently replacing pure physics with scripted/hybrid motion. Physics engines jitter, tunnel and explode at edge cases.
- **Character animation**: placeholder animation is easy; fluid, responsive animation needs motion matching or large blend trees, IK, root-motion handling and lots of authored/captured clips. AI-generated or procedural animation usually looks floaty or robotic without heavy clean-up.
- **Online multiplayer**: needs authoritative server or rollback, lag compensation, prediction, desync handling, matchmaking, hosting cost, anti-cheat. Retrofitting networking onto a single-player game is very hard - decide up front.
- **Procedural generation**: generating content is easy; generating content that is *interesting* and not samey is hard.
- **"Smart" NPC AI / LLM NPCs**: latency, cost per interaction, inconsistency, content safety, and staying within game logic.
- **Open worlds**: streaming, memory, content volume, traversal tuning.
- **Destructible environments, fluid/cloth simulation**: performance and stability.
- **Realistic graphics on a solo budget**: asset production, not rendering tech, is the bottleneck.
- **Cross-platform (esp. consoles/mobile)**: dev kits, certification, input differences, performance budgets.

**Typical budgets:** 60 fps = 16.6 ms/frame (30 fps = 33 ms, 120 fps = 8.3 ms); mobile thermal throttling; VR needs stable 72-120 fps.

## Web / desktop / mobile apps
**Systems:** UI, state management, routing, backend/API, database & schema, auth, file storage, real-time updates, notifications, payments, admin tools, search, background jobs, deployment/hosting, monitoring.

**Sounds easy, often disappoints:**
- **Real-time sync / collaborative editing**: conflict resolution (CRDT/OT), offline merge, presence.
- **Offline-first mobile apps**: sync conflicts, storage limits, background restrictions (iOS especially).
- **Background tasks on mobile**: OS kills/limits them; iOS is very restrictive.
- **"Scrape site X"**: ToS, anti-bot measures, layout changes break it.
- **Cross-platform UI frameworks**: native feel, platform-specific bugs, plugin gaps.
- **Payments & subscriptions**: tax, refunds, store rules (in-app purchase requirements), webhooks, edge cases.
- **Search that "just works"**: relevance tuning, typo tolerance, scale.
- **Browser capabilities**: Safari/iOS gaps in Web APIs (WebGPU, Web Bluetooth/USB/Serial, background audio, push), autoplay policies, CORS.

## Streaming / overlays / creator tools
**Systems:** platform APIs (Twitch, YouTube, Kick, TikTok etc.), OAuth & token refresh, event subscriptions (EventSub/webhooks/WebSockets), chat bots, overlays (browser sources in OBS/Streamlabs), OBS WebSocket control, alerts, counters/state persistence, moderation, rate limits.

**Sounds easy, often disappoints:**
- **Unified multi-platform features**: each platform exposes different data; some (e.g. TikTok Live, Kick) have limited or unofficial APIs that can break or violate ToS.
- **"Real-time" stats**: polling limits, webhook delays, viewer counts that platforms cache or hide.
- **Browser-source overlays**: OBS's embedded Chromium version/feature gaps, performance cost while gaming/encoding on the same PC.
- **Bots acting on behalf of users**: scopes, verification requirements, rate limits, moderation rules.
- **Hosting**: webhooks need a public HTTPS endpoint; a local-only app can't receive them without a tunnel or relay.
- **Encoding/compositing on the gaming PC**: CPU/GPU contention reduces game FPS.

## AI / ML features
**Systems:** model choice (API vs local), prompt/agent design, retrieval/data pipeline, evaluation, latency, cost, safety/moderation, fallback behaviour, privacy.

**Sounds easy, often disappoints:**
- **"AI does X reliably"**: demos are easy; consistent quality on real inputs needs evals and iteration. Hallucination, drift between model versions.
- **Local models**: VRAM requirements, speed on consumer GPUs, quality gap vs frontier APIs.
- **Real-time AI** (voice, vision, in-game): latency budgets often exceeded.
- **Training/fine-tuning your own model**: data collection and labelling dominate effort.
- **Generated art/animation/audio as final assets**: consistency, style control, licence questions, clean-up time.
- **Cost at scale**: per-request costs multiplied by users.

## Real-time / networking / media
- Latency vs bandwidth vs reliability trade-offs; NAT traversal for P2P; TURN relay costs.
- Audio/video: codecs, hardware encoder support, sync, echo cancellation.
- Clock sync, jitter buffers, packet loss handling.

## Hardware / embedded / devices
- Driver and SDK availability per OS; vendor SDK licences; supply/availability of hardware.
- USB/Bluetooth/serial permissions (especially browsers and mobile).
- Debugging needs physical access - AI agents in a cloud environment cannot touch the device.
- Power, thermals, real-time constraints.

## Data / backend at scale
- Expected load (requests/s, concurrent users, data size); database choice and indexing; caching; queueing; cost curve.
- Data protection (GDPR/COPPA if minors), backups, migrations.
