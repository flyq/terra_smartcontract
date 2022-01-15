# Terra SmartContract


To understand the framework better, please read the overview in the
[cosmwasm repo](https://github.com/CosmWasm/cosmwasm/blob/master/README.md),

## Creating a new repo from template

Assuming you have a recent version of rust and cargo (v1.51.0+) installed
(via [rustup](https://rustup.rs/)),
then the following should get you a new repo to start a contract:


```sh
cargo install cargo-generate cargo-run-script --features vendored-openssl 
```

**Latest: 0.16**

```sh
cargo generate --git https://github.com/CosmWasm/cw-template.git --name PROJECT_NAME
````

**Older Version**

Pass version as branch flag:

```sh
cargo generate --git https://github.com/CosmWasm/cw-template.git --branch <version> --name PROJECT_NAME
````

Example:

```sh
cargo generate --git https://github.com/CosmWasm/cw-template.git --branch 0.14 --name PROJECT_NAME
```

You will now have a new folder called `PROJECT_NAME` (I hope you changed that to something else)
containing a simple working contract and build system that you can customize.

## build

### build wasm
```bash
cargo wasm 
```

Optimizing the wasm size:
1. start the docker service

2. run:
```bash
cargo run-script optimize
```
result in `./artifacts/`

### build ABI interface (schema)
```bash
cargo schema
```

result in `./schema/`

