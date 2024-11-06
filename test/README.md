cd ..

<install rust>

<install wasmtime>

cargo build --release

cd tests/simple

make

time ~/.wasmtime/bin/wasmtime run --preload weval=../../lib/weval-stubs.wat simple.wasm

> real    0m2.066s 

time ~/.wasmtime/bin/wasmtime run simple-wevaled.wasm

> real    0m0.170s