# hal-infra-showcase

# HAL∞ (P2P Messenger)

Decentralized, private P2P messenger with zero-config onboarding and E2E encryption. Built with Rust, Android (Kotlin/JNI), and Tauri (Desktop).

## Architecture
*   **Core:** Rust (Tokio, Async)
*   **Transport:** Custom TCP/TLS, WebSocket (WSS) over Cloudflare Tunnels, UDP (LAN Discovery)
*   **Discovery:** Mainline BitTorrent DHT (BEP 5) for global peer lookup
*   **Security:** E2E encryption (Ratchet), TLS identity pinning, SAS pairing

## Project Structure
*   `crates/hal-sync` — Core sync engine, networking, and DHT routing.
*   `crates/hal-crypto` — Cryptographic primitives and key management.
*   `crates/hal-android` — Android JNI bindings and native runtime.
*   `crates/hal-desktop` — Tauri-based desktop client.
*   `crates/hal-relay` — Headless relay server for NAT traversal (Dockerized).

## Quick Start (Relay Server)
To run the standalone relay server via Docker:
```bash
docker-compose up -d
