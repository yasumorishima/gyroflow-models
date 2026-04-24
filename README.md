# gyroflow-models

AI optical flow model weights (`.bpk` format for [burn](https://burn.dev/) 0.21.0-pre.3) used by [gyroflow](https://github.com/gyroflow/gyroflow) when built with the `ai-optical-flow` feature.

## Why this repo exists

gyroflow ships as a compact library. Embedding the 145 MB gmflow weights directly into the shared library would bloat every user's install — including users who do not use AI-based optical flow. This repo hosts the weights as GitHub release assets so that gyroflow downloads them at runtime only on first use and caches them locally.

Pattern is modeled after gyroflow's existing [Lens Profile Database](https://github.com/gyroflow/lens_profiles).

## Models

| File | Size | Source | SHA-256 |
|---|---|---|---|
| `gmflow-scale2-regrefine6-320x576-opset16-sim.bpk` | 145 MB | UniMatch `gmflow-scale2-regrefine6` (pre-trained on Sintel/FlyingThings3D/KITTI) | `31feee698842928715e9ba693b69a492d85ace31c646df6f3eabd53e240cd5e9` |

Input: 320×576 RGB-replicated grayscale pair → Output: 2×320×576 flow tensor. ~7.4 M parameters.

## Attribution

The model weights are derived from **UniMatch** by Haofei Xu et al. (Max Planck Institute / Autonomous Vision Group, ETH Zürich). See [`NOTICE`](NOTICE) for the upstream MIT license notice. Please cite the original paper when using these weights:

> Haofei Xu, Jing Zhang, Jianfei Cai, Hamid Rezatofighi, Fisher Yu, Dacheng Tao, Andreas Geiger. *Unifying Flow, Stereo and Depth Estimation*. TPAMI 2023.

## License

Weight conversion, scripts and documentation in this repo: **MIT** (see [`LICENSE`](LICENSE)).
Original `.pth` weights: **MIT** (inherited from [autonomousvision/unimatch](https://github.com/autonomousvision/unimatch)).

## Reporting abuse

Unsolicited comments, unrelated bounty pitches, or requests for write access will be reported as spam. Interaction is limited to collaborators.
