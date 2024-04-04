# Smart contract for ERC20 Token

## Steps

Add the rust-src compiler component:

```bash
rustup component add rust-src
```

Install the latest version of cargo-contract:

```bash
cargo install --force --locked cargo-contract --version 4.0.2
```

Verify the installation and explore the commands available by running the following command:

```bash
cargo contract --help
```

Install the substrate-contract-node

```bash
cargo install contracts-node --git https://github.com/paritytech/substrate-contracts-node.git --tag v0.39.0
 --force --locked

```

Run the substrate-contract-node

```bash
substrate-contracts-node --log info,runtime::contracts=debug 2>&1
```

## Setup

Build the contract

```bash
cargo contract build
```

Instantiate the contract with the node already running

```bash
cargo contract instantiate --constructor new --args 100000 --suri //Alice --salt $(date +%s) -x
```

## Smart Contract Commands

> Update the --contract parameter corresponding to the contract value obtained when instantiated
> <br/>

### Get Commands

total_supply:

```bash
cargo contract call --contract 5CvDQFoxW1mMsbqKYHNEeWZysbZ1duVRUF2hNkxV9FhhEsxY --message total_supply --suri //Alice --skip-dry-run
```

balance_of:

```bash
cargo contract call --contract 5CvDQFoxW1mMsbqKYHNEeWZysbZ1duVRUF2hNkxV9FhhEsxY --message balance_of --args 5GrwvaEF5zXb26Fz9rcQpDWS57CtERHpNehXCPcNoHGKutQY --suri //Alice --skip-dry-run
```

```bash
cargo contract call --contract 5CvDQFoxW1mMsbqKYHNEeWZysbZ1duVRUF2hNkxV9FhhEsxY --message balance_of --args 5FHneW46xGXgs5mUiveU4sbTyGBzmstUspZC92UhjJM694ty --suri //Bob --skip-dry-run
```

allowance:

```bash
cargo contract call --contract 5CvDQFoxW1mMsbqKYHNEeWZysbZ1duVRUF2hNkxV9FhhEsxY --message allowance --args 5GrwvaEF5zXb26Fz9rcQpDWS57CtERHpNehXCPcNoHGKutQY 5GrwvaEF5zXb26Fz9rcQpDWS57CtERHpNehXCPcNoHGKutQY --suri //Alice --skip-dry-run
```

### Write Commands

transfer:

```bash
cargo contract call --contract 5CvDQFoxW1mMsbqKYHNEeWZysbZ1duVRUF2hNkxV9FhhEsxY --message transfer --args 5FHneW46xGXgs5mUiveU4sbTyGBzmstUspZC92UhjJM694ty 1000 --suri //Alice -x
```

transfer_from:

```bash
cargo contract call --contract 5CvDQFoxW1mMsbqKYHNEeWZysbZ1duVRUF2hNkxV9FhhEsxY --message transfer_from --args 5GrwvaEF5zXb26Fz9rcQpDWS57CtERHpNehXCPcNoHGKutQY 5FHneW46xGXgs5mUiveU4sbTyGBzmstUspZC92UhjJM694ty 1000 --suri //Alice -x
```

approve:

```bash
cargo contract call --contract 5CvDQFoxW1mMsbqKYHNEeWZysbZ1duVRUF2hNkxV9FhhEsxY --message approve --args 5GrwvaEF5zXb26Fz9rcQpDWS57CtERHpNehXCPcNoHGKutQY 10000 --suri //Alice -x
```

```bash
cargo contract call --contract 5CvDQFoxW1mMsbqKYHNEeWZysbZ1duVRUF2hNkxV9FhhEsxY --message approve --args 5GrwvaEF5zXb26Fz9rcQpDWS57CtERHpNehXCPcNoHGKutQY 10000 --suri //Bob -x
```
