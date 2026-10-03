# Technical Architecture — CLO3D_SDK

**Upstream:** [https://github.com/nicedoc/clo3d-sdk](https://github.com/nicedoc/clo3d-sdk)
**License:** MIT
**Category:** CLOTHING_MANUFACTURING
**Anticloud Integration:** PAX L5 Narrow L2 General 27B + AIOSS + Offline-First

## Upstream Description

CLO 3D garment simulation SDK bindings

## Anticloud Architectural Changes

1. PAX L5 Narrow L2 General 27B local defect detection on production line
2. AIOSS tamper-evident quality control log per garment batch
3. AES-256 encryption for all pattern and specification files
4. Single-binary MES deployable on factory floor PCs
5. Zero-cloud: all vision inspection and reporting run locally
6. GPU/CPU equalizer: vision AI on GPU, telemetry on CPU
7. Open pattern format: DXF/AAMA export replacing proprietary CAD lock-in
8. Offline sustainable materials database for supply chain sourcing

## Integration Points

- **PAX Inference Socket:** Local HTTP endpoint at `127.0.0.1:11434/v1/chat` — same OpenAI-compatible API, zero cloud
- **AIOSS Hook:** Every write operation calls `aioss_append(event, payload)` before commit
- **Encryption Layer:** All file I/O routed through `anticloud_crypto.encrypt_at_rest()`
- **Single Binary Build:** `pyinstaller anticloud_clo3d_sdk.spec` or `go build -o clo3d_sdk`

## Deployment Modes

| Mode | Hardware | Notes |
| --- | --- | --- |
| Edge CPU | Raspberry Pi 4 / Intel NUC | Full feature set, PAX on CPU |
| Desktop GPU | RTX 3060 / A10 | PAX GPU inference, <1s latency |
| Server | 2× A100 | Full batch throughput |
| Air-gapped | Any x86/ARM | Zero network dependency |