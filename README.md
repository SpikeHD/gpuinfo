<div align="center">
  <h1>gpuinfo</h1>
  <p>
    Rust library for querying GPU information
  </p>
</div>

<div align="center">
  <img src="https://img.shields.io/github/actions/workflow/status/SpikeHD/gpuinfo/format.yml?label=code quality" />
</div>

# TL;DR

```rust
use gpuinfo::active_gpu;

let gpu = active_gpu();
println!("GPU vendor: {}", gpu.vendor());
println!("GPU model: {}", gpu.model());
println!("GPU family: {}", gpu.family());
println!("GPU device ID: {}", gpu.device_id());

// And with `gpu_info` feature enabled
let info = gpu.info();
println!("Total VRAM: {} bytes", info.total_vram());
println!("Used VRAM: {} bytes", info.used_vram());
println!("Load: {}%", info.load_pct());
println!("Temperature: {} C", info.temperature() / 1000);
```

# Features

* Cross-platform, cross-vendor support
* Plenty of feature flags
* Low dependency count

# Feature flags

| Feature | Description | Default |
| --- | --- | --- |
| `default` | Enables all features | Yes |
| `amd` | Enables AMD GPU support | Yes |
| `nvidia` | Enables Nvidia GPU support | Yes |
| `intel` | Enables Intel GPU support | Yes |
| `gpu_info` | Enables the `GpuInfo` trait, which provides query functions for things like VRAM usage | Yes |

# TODO

(Windows support is speculative, as it uses the Windows API and I don't have a Windows machine to test on. It did work partially in a VM using the basic display driver!)

* [ ] Cross-platform vendor support
  * [x] Nvidia
    * [x] Windows
    * [x] Linux 
  * [x] AMD
    * [x] Windows
    * [x] Linux
  * [ ] Intel
    * [x] Windows
    * [ ] Linux
  * [ ] Generic/Other
* [ ] Supported information
  * [x] Vendor
  * [x] Model
  * [x] Family
  * [x] Device ID
  * [x] Total VRAM
  * [x] Used VRAM
  * [x] Load percentage
  * [x] Temperature