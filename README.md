# @_koii/namespace-wrapper

## Project Overview

`@_koii/namespace-wrapper` is a powerful utility package designed for building and managing decentralized tasks within the Koii Network ecosystem. This library provides a comprehensive abstraction layer for task node operations, offering developers an intuitive interface for interacting with blockchain-based distributed computing environments.

### Key Features
- 🔒 Secure task node management
- 💾 Persistent data storage with NeDB
- 🌐 Flexible blockchain interaction
- 🔄 Cross-environment compatibility (task node and local testing)
- 📋 Comprehensive utility functions for task submissions, distribution, and auditing

## Installation

Install the package using npm or yarn:

```bash
npm install @_koii/namespace-wrapper
# or
yarn add @_koii/namespace-wrapper
```

### Prerequisites
- Node.js (v16+ recommended)
- Access to a Koii Network task node environment
- Web3.js compatible environment

## API Reference

### NamespaceWrapper Class

The `NamespaceWrapper` is the primary class for task node interactions. Here are its key methods:

#### Storage Methods
- `storeGet(key: string)`: Retrieve a value by key
  ```typescript
  const value = await namespaceWrapper.storeGet('myKey')
  ```

- `storeSet(key: string, value: string)`: Store a key-value pair
  ```typescript
  await namespaceWrapper.storeSet('myKey', 'myValue')
  ```

#### Blockchain Interaction Methods
- `getTaskState(options: TaskStateOptions)`: Fetch current task state
  ```typescript
  const taskState = await namespaceWrapper.getTaskState({})
  ```

- `getSubmitterAccount()`: Get the current task submitter's account
  ```typescript
  const submitterAccount = await namespaceWrapper.getSubmitterAccount()
  ```

#### Submission and Distribution Methods
- `validateAndVoteOnNodes(validate, round)`: Validate and vote on task submissions
- `selectAndGenerateDistributionList(submitDistributionList, round, isPreviousRoundFailed)`: Select and generate distribution list

#### Cryptographic Methods
- `payloadSigning(body, privateKey)`: Sign payload data
- `verifySignature(signedMessage, pubKey)`: Verify cryptographic signatures

### Exported Constants
- `taskNodeAdministered`: Boolean indicating task node administration state
- `TASK_ID`: Current task identifier
- `MAIN_ACCOUNT_PUBKEY`: Main account public key
- `K2_NODE_URL`: Koii network node URL

## Repository Structure
```
.
├── src/                  # Source code
│   ├── index.ts          # Main library entry point
│   └── types.ts          # TypeScript type definitions
├── webasm_bincode_deserializer/  # WebAssembly utilities
├── package.json          # Project configuration
└── tsconfig.json         # TypeScript compiler configuration
```

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add some feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

### Running Tests
Currently, no specific test suite is configured. Use `npm test` to run default checks.

## License

This project is licensed under the ISC License. See the LICENSE file for details.

## Powered by Koii Network 🚀