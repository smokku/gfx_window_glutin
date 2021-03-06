# What is different with this repo?

Updated code and dependencies so that you can use the latest at the time:
```toml
glutin = "0.25.0"
winit = "0.23.0"
gfx_core = "0.9.1"
gfx_device_gl = "0.16.2"
```

# Original repo:

# gfx_window_glutin

Glutin window backend for gfx-rs

## Usage

Make sure you have the following in your `Cargo.toml`:

```toml
glutin = "0.25.0"
winit = "0.23.0"
gfx_core = "0.9.1"
gfx_device_gl = "0.16.2"
```

Then, initialize `gfx` as follows:

```rust
extern crate gfx_core;
extern crate gfx_device_gl;
extern crate gfx_window_glutin;
extern crate glutin;

use gfx_core::format::{DepthStencil, Rgba8};

fn main() {
    let events_loop = glutin::EventsLoop::new();
    let window_builder = glutin::WindowBuilder::new().with_title("Example".to_owned());
    let context = glutin::ContextBuilder::new();
    let (window, device, factory, rtv, stv) =
        gfx_window_glutin::init::<Rgba8, DepthStencil>(window_builder, context, &events_loop);

    // your code
}
```
