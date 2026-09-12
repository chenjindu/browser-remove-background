# Browser Remove Background

Removes image backgrounds **entirely in your browser** — the image is decoded,
segmented and composited on your own device. Nothing is uploaded, no server,
no API key, no account.

Built with [ONNX Runtime Web](https://onnxruntime.ai/docs/tutorials/web/)
running the ISNet segmentation model (Apache-2.0), with both WASM and WebGPU
execution providers.

## Live tool

A production version of this runs at **[https://is.tools/remove-background](https://is.tools/remove-background)**
— free, no signup, no watermark, no size cap.

## Run it locally

    npx serve .

Then open http://localhost:3000, pick a photo, and run inference with WASM
and with WebGPU to compare.

## Benchmark

Measured on a desktop with a discrete GPU (Chrome 113+):

| Execution provider | 2nd inference |
|---|---|
| WebGPU | ~0.6 s |
| WASM   | ~17 s  |

The first run is always slower — shader compilation and model warm-up. Read
the second number.

## Requirements

WebGPU needs Chrome or Edge 113+. Without it the page falls back to WASM,
which works everywhere but is roughly 25× slower.

## License

Apache-2.0
