# @_koii/namespace-wrapper

## Project Overview

`@_koii/namespace-wrapper` is a robust utility library designed for Koii Network task developers, providing a comprehensive set of tools and abstractions to simplify building and managing decentralized tasks. This library acts as a middleware between task developers and the Koii Network infrastructure, offering seamless interaction with blockchain and decentralized computation environments.

### Key Features

- **Cross-Environment Compatibility**: Works consistently in both task node administered and local testing environments
- **Blockchain Interaction**: Simplified methods for transaction handling, staking, and network interactions
- **Data Management**: Built-in database and file system utilities
- **Cryptographic Utilities**: Signature verification, encoding/decoding helpers
- **Logging and Debugging**: Advanced logging mechanisms with multiple log levels
- **Task State Management**: Comprehensive methods for tracking task submissions, distributions, and audits

## Installation

Install the library using npm:

```bash
npm install @_koii/namespace-wrapper
```

Or using yarn:

```bash
yarn add @_koii/namespace-wrapper
```

### Prerequisites

- Node.js (v16 or higher)
- TypeScript (recommended)
- Access to Koii Network infrastructure

## API Reference

### Core Namespace Wrapper Class

#### Initialization
```typescript
import { namespaceWrapper } from '@_koii/namespace-wrapper'
```

#### Database Methods
- `getDb()`: Get the database instance
- `storeSet(key: string, value: string)`: Store a key-value pair
- `storeGet(key: string)`: Retrieve a value by key

#### Blockchain Interaction Methods
- `sendTransaction(serviceNodeAccount, beneficiaryAccount, amount)`: Send a transaction
- `stakeOnChain(taskStateInfoPublicKey, stakingAccKeypair, stakePotAccount, stakeAmount)`: Stake tokens on the network
- `getTaskState(options)`: Retrieve current task state

#### Cryptographic Utilities
- `bs58Encode(data)`: Encode data to base58
- `bs58Decode(data)`: Decode base58 data
- `verifySignature(signedMessage, pubKey)`: Verify cryptographic signatures

#### Logging
- `logger(level: LogLevel, message: string, action: string)`: Log messages with different severity levels

### Enums and Types
```typescript
enum LogLevel {
  Log = 'log',
  Warn = 'warn',
  Error = 'error'
}

interface TaskState {
  task_id: string
  task_name: string
  is_active: boolean
  current_round: number
  // ... other properties
}
```

## Repository Structure

- `src/index.ts`: Main library implementation
- `src/types.ts`: TypeScript type definitions
- `webasm_bincode_deserializer/`: WebAssembly and bincode deserialization utilities
- `package.json`: Project configuration and dependencies

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add some feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

### Running Tests

Currently, the library does not have a specified test suite. We recommend setting up tests using Jest or a similar testing framework.

## License

This project is licensed under the ISC License. See the LICENSE file for details.

## Support

For support, please open an issue in the GitHub repository or join the Koii Network community channels.