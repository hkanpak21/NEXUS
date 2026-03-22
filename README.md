# Multi-GPU/Multi-Node NEXUS
Extended from [original NEXUS](https://github.com/zju-abclab/NEXUS) for distributed execution per study.md roadmap.

## Baseline Reproduction
```bash
cd cuda
mkdir build && cd build
cmake .. -DCMAKE_CUDA_ARCHITECTURES=75  # T4 GPU
make -j
./bin/main  # Tests MatMul etc. (set TEST_TARGET_IDX in main.cu)
```

## Dependencies
- CUDA 13
- NCCL (linked)
- Phantom-FHE (bundled)
- NTL, GMP (apt installed)

## Next: Multi-GPU Scaling
Implement RNS limb parallelism in Phantom NTT/key-switching, NCCL input-broadcast/output-aggregation.

Run baseline MatMul test to verify.
