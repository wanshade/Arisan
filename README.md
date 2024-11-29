# Arisan Smart Contract

## Overview

This smart contract implements a decentralized version of the traditional Indonesian Arisan system, bringing the community-based rotating savings and credit association (ROSCA) concept to the blockchain. Built for Base Sepolia testnet, the contract allows users to create, join, and participate in Arisan groups with transparent and automated fund management.

## Features

- **Group Creation**: Create Arisan groups with customizable parameters
- **Transparent Participation**: 
  - Fixed contribution amounts
  - Member limit controls
  - Fair winner selection
- **Secure Transactions**: 
  - Prevents duplicate memberships
  - Ensures equal contributions
  - Pseudorandom winner selection

## Contract Functions

### `createArisanGroup(string _name, uint256 _contributionAmount, uint256 _memberLimit)`
- Creates a new Arisan group
- Parameters:
  - `_name`: Name of the Arisan group
  - `_contributionAmount`: Fixed amount each member must contribute
  - `_memberLimit`: Maximum number of group members

### `joinArisanGroup(uint256 _groupId)`
- Join an existing Arisan group
- Requires paying the exact contribution amount
- Prevents joining full groups or duplicate memberships

### `contribute(uint256 _groupId)`
- Make a contribution to an existing group
- Ensures only group members can contribute
- Validates correct contribution amount

### `drawWinner(uint256 _groupId)`
- Selects a winner for the current period
- Ensures:
  - Group is full
  - Each member wins only once per cycle
  - Distributes total collected funds to the winner

### Utility Functions
- `getGroupMembers(uint256 _groupId)`: Retrieve list of group members
- `getGroupDetails(uint256 _groupId)`: Get comprehensive group information

## Prerequisites

- Solidity ^0.8.20
- OpenZeppelin Contracts
- Base Sepolia Testnet environment

## Installation

1. Clone the repository
2. Install dependencies:
   ```bash
   npm install @openzeppelin/contracts
   ```

## Deployment

1. Compile the contract using Hardhat or Truffle
2. Deploy to Base Sepolia testnet
3. Verify contract on Base Sepolia block explorer

## Security Considerations

- Contract uses OpenZeppelin's `Ownable` and `ReentrancyGuard`
- Pseudorandom winner selection (potential for future improvement)
- Strict checks on group creation and participation

## Potential Improvements

- Implement Chainlink VRF for true randomness
- Add slashing mechanisms for non-contributors
- Introduce time-based constraints
- Implement multi-period Arisan cycles

## Testnet Deployment

### Base Sepolia Testnet Details
- Network: Base Sepolia
- Purpose: Testing and demonstration

## Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a new Pull Request

## License

MIT License

## Disclaimer

This is a community project and comes with no guarantees. Use at your own risk. Always conduct thorough testing before real-world deployment.

## Contact

For issues, suggestions, or collaborations, please open a GitHub issue or contact the maintainers.
