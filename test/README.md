cd ..

<install rust>

<install wasmtime>

cargo build --release

cd tests/simple

make

time ~/wasmtime run --preload weval=../../lib/weval-stubs.wat simple.wasm

> end state: 100000000
> real    0m2.066s 

time ~/wasmtime run simple-wevaled.wasm

> end state: 100000000
> real    0m0.170s

<install wazero>

time ~/wazero run -interpreter simple-wevaled.wasm

> end state: 10000000
> real    0m2.775s

time ~/wazero run -interpreter simple-noweval.wasm

> end state: 10000000
> real    0m20.593s