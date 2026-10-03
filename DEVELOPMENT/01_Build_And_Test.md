# Build and Test

**Project:** `CLO3D_SDK`
**Upstream:** https://github.com/nicedoc/clo3d-sdk
**License:** MIT

## Quick Start

```bash
git clone https://github.com/nicedoc/clo3d-sdk
cd clo3d-sdk
pip install -r requirements-anticloud.txt
python anticloud_main.py --offline --pax-local
```

## Anticloud Improvements Applied

1. PAX L5 Narrow L2 General 27B local defect detection on production line
2. AIOSS tamper-evident quality control log per garment batch
3. AES-256 encryption for all pattern and specification files
4. Single-binary MES deployable on factory floor PCs
5. Zero-cloud: all vision inspection and reporting run locally
6. GPU/CPU equalizer: vision AI on GPU, telemetry on CPU
7. Open pattern format: DXF/AAMA export replacing proprietary CAD lock-in
8. Offline sustainable materials database for supply chain sourcing

## Benchmark Targets

| Metric | Target |
| --- | --- |
| Latency | Primary inference task: <5s on CPU, <1s on GPU |
| Throughput | Batch processing: >100 items/hour on single CPU server |
| Memory | <8GB RAM for standard deployment |
| Accuracy | Task-specific accuracy within 5% of cloud-API baseline |

## Build Status

Not yet measured. Run verified build and record actual figures above.
