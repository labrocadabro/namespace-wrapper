# Koii Namespace Wrapper

## Project Overview

The Koii Namespace Wrapper is a comprehensive utility library designed to simplify and streamline task development and management on the Koii Network. It provides a robust set of tools and abstractions that help developers create decentralized tasks with minimal overhead, handling complex blockchain interactions and task lifecycle management.

### Key Features

- **Blockchain Interaction**: Seamless integration with Koii's blockchain infrastructure
- **Task State Management**: Simplified methods for handling task states, submissions, and distributions
- **Cross-Environment Support**: Works consistently in both task node and local testing environments
- **Comprehensive Utility Functions**: Includes methods for file system interactions, data storage, cryptographic operations, and more
- **Flexible Configuration**: Supports various task types and network configurations

## Installation

You can install the Namespace Wrapper using npm or yarn:

```bash
npm install @_koii/namespace-wrapper
# or
yarn add @_koii/namespace-wrapper
```

### Prerequisites

- Node.js (version 16 or higher)
- TypeScript
- Access to Koii Network resources

## Usage Examples

### Basic Task Setup

```typescript
import { namespaceWrapper } from '@_koii/namespace-wrapper';

// Initialize your task state
async function setupTask() {
  // Get the current task state
  const taskState = await namespaceWrapper.getTaskState({});
  
  // Check submission and update round
  await namespaceWrapper.checkSubmissionAndUpdateRound('submission_value', 1);
}
```

### File System Interactions

```typescript
import { namespaceWrapper } from '@_koii/namespace-wrapper';

// Read a file using namespace wrapper
async function readTaskFile() {
  const fileContent = await namespaceWrapper.fs('readFile', '/path/to/file');
  console.log(fileContent);
}
```

### Data Storage

```typescript
import { namespaceWrapper } from '@_koii/namespace-wrapper';

// Store and retrieve data
async function manageData() {
  // Store a key-value pair
  await namespaceWrapper.storeSet('key', 'value');
  
  // Retrieve a value
  const value = await namespaceWrapper.storeGet('key');
  console.log(value);
}
```

## API Reference

### Core Methods

- `getTaskState(options)`: Retrieve the current task state
- `checkSubmissionAndUpdateRound(submissionValue, round)`: Update task round
- `fs(method, path, ...args)`: File system interactions
- `storeSet(key, value)`: Store a key-value pair
- `storeGet(key)`: Retrieve a value by key
- `payloadSigning(body, privateKey?)`: Sign payload data

### Utility Methods

- `bs58Encode(data)`: Encode data to base58
- `bs58Decode(data)`: Decode base58 data
- `verifySignature(signedMessage, pubKey)`: Verify cryptographic signatures

## Repository Structure

- `src/`: TypeScript source files
  - `index.ts`: Main library implementation
  - `types.ts`: Type definitions
- `webasm_bincode_deserializer/`: WebAssembly and bincode-related utilities
- `package.json`: Project configuration and dependencies

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Create a Pull Request

### Running Tests

Currently, no specific test suite is configured. Ensure you have the necessary Koii Network environment set up for testing.

## License

This project is licensed under the ISC License. See the LICENSE file for details.

## Contact

For more information, visit [Koii Network](https://koii.network) or join their developer community.