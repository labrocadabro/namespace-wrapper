# @_koii/namespace-wrapper

## Project Overview

The `@_koii/namespace-wrapper` is a powerful utility package designed for developers working with Koii Network tasks. This library provides a comprehensive wrapper for task node operations, offering a seamless interface for blockchain interactions, data management, and task state handling.

### Key Features

- **Task Node Management**: Simplifies task node administration and interaction
- **Blockchain Compatibility**: Works with Koii Network's blockchain infrastructure
- **Cross-Environment Support**: Supports both task node and local testing environments
- **Comprehensive Utility Functions**: Provides methods for storage, transaction handling, logging, and more
- **Flexible Configuration**: Easily adaptable to different task requirements

## Installation

Install the library using npm or yarn:

```bash
npm install @_koii/namespace-wrapper
# or
yarn add @_koii/namespace-wrapper
```

### Prerequisites

- Node.js (version 16 or later)
- A valid Koii Network task configuration
- Basic understanding of blockchain and task node concepts

## Usage Examples

### Basic Initialization

```typescript
import { namespaceWrapper } from '@_koii/namespace-wrapper';

// Store a key-value pair
await namespaceWrapper.storeSet('myKey', 'myValue');

// Retrieve a stored value
const storedValue = await namespaceWrapper.storeGet('myKey');
```

### Transaction and Signature Handling

```typescript
// Sign a payload
const signedPayload = await namespaceWrapper.payloadSigning({
  data: 'Example payload'
});

// Verify a signature
const verificationResult = await namespaceWrapper.verifySignature(
  signedPayload, 
  publicKey
);
```

### Task State Management

```typescript
// Get current task state
const taskState = await namespaceWrapper.getTaskState({
  is_submission_required: true,
  is_distribution_required: true
});
```

## API Reference

### Core Methods

#### Storage
- `storeSet(key: string, value: string)`: Store a key-value pair
- `storeGet(key: string)`: Retrieve a value by key

#### Blockchain Interactions
- `sendTransaction(...)`: Send a blockchain transaction
- `stakeOnChain(...)`: Stake tokens on a task
- `claimReward(...)`: Claim rewards for a task

#### File System
- `fs(method, path, ...args)`: Perform file system operations
- `fsWriteStream(imagepath)`: Create a write stream
- `fsReadStream(imagepath)`: Read a file stream

#### Cryptography
- `payloadSigning(body, privateKey?)`: Sign a payload
- `verifySignature(signedMessage, pubKey)`: Verify a signature
- `bs58Encode(data)`: Encode data to base58
- `bs58Decode(data)`: Decode base58 data

#### Task Management
- `getTaskState(options)`: Retrieve current task state
- `getSubmitterAccount()`: Get the submitter's account
- `validateAndVoteOnNodes(...)`: Validate and vote on task submissions
- `selectAndGenerateDistributionList(...)`: Manage task distribution

### Enums and Types

- `LogLevel`: Logging levels (Log, Warn, Error)
- `TaskType`: Task types (KPL, KOII)
- `TaskState`: Comprehensive task state interface
- `TaskSubmissionState`: Submission-related state
- `TaskDistributionInfo`: Distribution-related information

## Repository Structure

- `src/index.ts`: Main library implementation
- `src/types.ts`: TypeScript type definitions
- `package.json`: Project configuration and dependencies
- `tsconfig.json`: TypeScript compiler configuration

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add some feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

### Running Tests

Currently, no specific test suite is configured. Contributions for adding comprehensive tests are highly appreciated.

## License

This project is licensed under the ISC License. See the LICENSE file for details.

## Disclaimer

This library is part of the Koii Network ecosystem and is intended for developers building decentralized tasks and applications.