```markdown
# Bike Parking Allotment Smart Contract

## Overview

This Smart Contract, written in Solidity, allows users to allot parking slots for their bikes within a specified range (10 to 50). It includes a special condition for Slot 31, reserved for VIPs, triggering a revert if attempted by non-VIP users.

## Features

- Allot bike parking slots within the range of 10 to 50.
- Special handling for Slot 31, reserved for VIPs.
- Events emitted for successful bike allotment.
- Ownership functionality to track the contract owner.

## Usage

### Constructor

- Initializes the contract owner with the address of the deployer.

### `allotBikeParking` Function

- Allots a parking slot for the caller.
- Checks if the requested slot is within the valid range.
- Special handling for Slot 31, reverting for non-VIP users.
- Requires that the requested slot is not already allotted to another user.

### `getBikeSlot` Function

- Retrieves the parking slot allotted to a specific bike owner.

## Getting Started

1. Deploy the contract to a compatible Ethereum Virtual Machine (EVM) such as Ethereum Mainnet or a testnet.
2. Use the `allotBikeParking` function to allot parking slots.
3. Query allotted slots using the `getBikeSlot` function.

## Example

```solidity
// Deploy the contract
const bikeParkingContract = await BikeParkingAllotment.deployed();

// Allot a parking slot (example: Slot 20)
await bikeParkingContract.allotBikeParking(20);

// Retrieve the allotted slot for a specific bike owner
const allottedSlot = await bikeParkingContract.getBikeSlot(ownerAddress);
console.log("Allotted Slot:", allottedSlot);
```

## License

This Smart Contract is released under the MIT License. See [LICENSE](LICENSE) for details.
```
