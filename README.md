# Sapling Migration Simulation

This script is intended to simulate strategies for migrating funds from the
Sprout to Sapling shielded pools on the Zcash blockchain.

## How it works

First we generate a mix of mock shielded and transparent transactions up to a
given Sapling activation height. We then continue to generate blocks in a
similar fashion but at the same time for each user/node we execute a strategy
for migrating Sprout shielded addresses to Sapling shielded addresses.
The script generates a minimal amount of information to execute and validate
the strategy.

As part of execution we write 3 files:

*blockchain.csv:*

>This csv file has four columns: "block_height", "txid", "inputs", "outputs".

>This file is a simplification of the information stored on the block chain.
"inputs" and "outputs" can be either transparent, sprout, or sapling. This
differs from the actual Zcash blockchain where each of these types are stored
separately.

*user\_balance\_\*.csv:*

>These csv files have four columns: "user_id", "sprout_balance",
"sapling_balance", and "transparent_balance".

>These files are intended to provide some insight to the mock data which is
generated, and to aid in validating the migration strategy. One file is
produced before the migration begins, and a second file is produced after
the simulation ends.

## Usage

After cloning, enter the following command to run the script and generate the
output files:

```
python simulator.py
```
