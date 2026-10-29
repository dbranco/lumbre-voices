# lumbre-voices

Voice models and WebAssembly files served to the Lumbre app (https://lumbre.pt) so the browser can read AI GM messages aloud with Piper. Everything runs on the listener's device; nothing here receives any text.

## Voices (`models/`)

| Language | Voice | Licence | Source |
|---|---|---|---|
| English (UK) | `en_GB-cori-medium` | public domain (LibriVox recordings) | https://huggingface.co/rhasspy/piper-voices |
| Spanish (Spain) | `es_ES-davefx-medium` | CC0 | https://huggingface.co/rhasspy/piper-voices |
| Portuguese (Portugal) | `pt_PT-tugao-medium` (`pt_PT-tugão-medium` upstream) | CC0 | https://huggingface.co/rhasspy/piper-voices |

Each `.onnx` file is byte-identical to the upstream file (its SHA-256 equals the upstream `x-linked-etag`). `SHA256SUMS` lists every file.

## WebAssembly (`wasm/`)

- `ort-wasm-simd-threaded.mjs` and `.wasm`: ONNX Runtime Web 1.31.1 (MIT), from the npm package `onnxruntime-web`.
- `piper_phonemize.wasm` and `.data`: from the npm package `@diffusionstudio/piper-wasm` 1.0.0 (MIT). They contain eSpeak NG (GPL-3.0, https://github.com/espeak-ng/espeak-ng), which turns text into phonemes; its source is at that address.
