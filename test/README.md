cd ..

<install rust>

<install wasmtime>

cargo build --release

cd tests/simple

make

time ~/wasmtime run simple-noweval.wasm

> end state: 10000008
> real    0m0.249s

time ~/wasmtime run simple-wevaled.wasm

> end state: 10000008
> real    0m0.058s

<install wazero>

time ~/wazero run -interpreter simple-noweval.wasm

> end state: 10000008
> real    0m20.593s

time ~/wazero run -interpreter simple-wevaled.wasm

> end state: 10000008
> real    0m2.775s
