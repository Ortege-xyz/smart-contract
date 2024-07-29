# Jetton Smart Contract (TEP-74 Compliant)

This repository contains a Jetton (fungible token) smart contract implementation that complies with the TON Ecosystem Proposal 74 (TEP-74) standard. The Jetton contract allows for the creation, transfer, and management of fungible tokens on the TON blockchain.

## Files

1. `jetton-master.fc`: The main Jetton master contract.
2. `op-codes.fc`: Operation codes used in the contract.
3. `params.fc`: Helper functions and parameters for the Jetton contract.

## Features

- Minting new tokens (admin only)
- Burning tokens
- Retrieving Jetton data
- Calculating wallet addresses

## Requirements

- FunC compiler
- TON development environment (e.g., TON CLI, TON Development Environment)

## Usage

1. Compile the contract:
   ```
   func -SPA -o jetton-master.fif jetton-master.fc op-codes.fc params.fc
   ```

2. Deploy the contract:
   Use your preferred method to deploy the contract to the TON blockchain. You'll need to provide the following initial data:
   - Total supply
   - Admin address
   - Content cell (following TEP-64 standard)
   - Jetton wallet code

3. Interacting with the contract:
   - Minting: Send an internal message with `op::mint()` operation code.
   - Burning: Jetton wallets will send burn notifications to the master contract.
   - Retrieving data: Use get-methods `get_jetton_data()` and `get_wallet_address()`.

## Customization

You can customize the Jetton by modifying the content cell to include specific metadata about your token, such as name, symbol, decimals, and other properties as defined in TEP-64.

## Security Considerations

- Only the admin can mint new tokens.
- Ensure proper access control when deploying and managing the contract.
- Thoroughly test the contract before deploying it to the main network.

## Compliance

This implementation aims to comply with TEP-74. However, always refer to the latest version of the standard and consider any updates or changes that may have occurred.
