# Command Line Interface — CLO3D_SDK

**Upstream:** https://github.com/nicedoc/clo3d-sdk

## Anticloud CLI

```bash
# Install
pip install anticloud-clo3d-sdk

# Run offline with PAX inference
anticloud-clo3d-sdk --offline --pax-local

# Run with AIOSS logging
anticloud-clo3d-sdk --aioss-log ./ledger.jsonl

# Single binary (after build)
./clo3d_sdk --config config.yaml
```

## Options

| Flag | Description |
| --- | --- |
| `--offline` | Disable all network calls |
| `--pax-local` | Use local PAX inference at 127.0.0.1:11434 |
| `--aioss-log PATH` | Write AIOSS audit chain to PATH |
| `--encrypt` | Enable AES-256 at rest for output files |
| `--gpu` | Force GPU inference |
| `--cpu` | Force CPU inference |
| `--config PATH` | Load configuration from YAML file |
