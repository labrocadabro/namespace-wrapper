# @_koii/namespace-wrapper

## Project Overview

`@_koii/namespace-wrapper` is a powerful TypeScript utility package designed to simplify and streamline task management and node interactions within the Koii Network ecosystem. This library provides developers with a comprehensive set of tools for building decentralized tasks, managing blockchain interactions, and handling distributed computing workflows.

### Key Features

- 🔒 Secure cryptographic operations and signature management
- 💾 Flexible data storage and retrieval using NeDB
- 🌐 Seamless interaction with Koii Network's blockchain infrastructure
- 🚀 Simplified task node administration
- 🔍 Advanced submission and distribution list validation
- 📊 Comprehensive task state management

## Installation

Install the library using npm or yarn:

```bash
npm install @_koii/namespace-wrapper
# or
yarn add @_koii/namespace-wrapper
```

### Prerequisites

- Node.js (v16 or later)
- TypeScript (v4.5 or later)
- Access to Koii Network infrastructure

## Usage Examples

### Basic Initialization

```typescript
import { namespaceWrapper } from '@_koii/namespace-wrapper';

// Initialize the namespace wrapper
const wrapper = namespaceWrapper;
```

### Storing and Retrieving Data

```typescript
// Store a key-value pair
await wrapper.storeSet('myKey', 'myValue');

// Retrieve a value
const value = await wrapper.storeGet('myKey');
```

### Task Submission Management

```typescript
// Check submission and update round
await wrapper.checkSubmissionAndUpdateRound('submissionValue', currentRound);

// Validate and vote on node submissions
await wrapper.validateAndVoteOnNodes(
  async (submissionValue, round, nodePublicKey) => {
    // Custom validation logic
    return true; // or false
  },
  currentRound
);
```

## API Reference

### Core Methods

- `storeSet(key: string, value: string)`: Store a key-value pair
- `storeGet(key: string)`: Retrieve a value by key
- `payloadSigning(body: Record<string, unknown>)`: Sign payload data
- `verifySignature(signedMessage: string, pubKey: string)`: Verify cryptographic signatures
- `getTaskState(options: TaskStateOptions)`: Retrieve current task state
- `validateAndVoteOnNodes(validate: Function, round: number)`: Validate and vote on node submissions
- `selectAndGenerateDistributionList(submitDistributionList: Function, round: number)`: Select and generate distribution lists

### Logging Methods

- `logger(level: LogLevel, message: string, action: string)`: Log messages with different severity levels

## Repository Structure

- `src/`: Source code directory
  - `index.ts`: Main library implementation
  - `types.ts`: TypeScript type definitions
- `webasm_bincode_deserializer/`: WebAssembly and binary code deserialization utilities
- `tsconfig.json`: TypeScript configuration
- `package.json`: Project metadata and dependencies

## Contributing

We welcome contributions! To contribute:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature`)
3. Make your changes
4. Run tests: `npm run test`
5. Commit your changes: `git commit -m 'Add some feature'`
6. Push to the branch: `git push origin feature/your-feature`
7. Open a Pull Request

### Running Tests

Currently, no specific test script is defined. Implement tests using your preferred testing framework.

## License

This project is licensed under the ISC License. See the [LICENSE](LICENSE) file for details.

## Contact

For more information, visit [Koii Network](https://www.koii.network)