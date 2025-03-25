# Koii Namespace Wrapper Library

## Project Overview

The Koii Namespace Wrapper is a powerful utility package designed to simplify and streamline the development of decentralized tasks and applications within the Koii Network ecosystem. This library provides a comprehensive set of tools and abstractions to interact with Koii's distributed computing infrastructure, making it easier for developers to build, deploy, and manage decentralized applications.

### Key Features

- 🔹 Simplified task node management
- 🔹 Integrated blockchain interactions
- 🔹 Robust data storage and retrieval mechanisms
- 🔹 Secure cryptographic utilities
- 🔹 Flexible task submission and distribution workflows
- 🔹 Cross-environment compatibility (task node and local testing)

## Installation

Install the library using npm or yarn:

```bash
# Using npm
npm install @_koii/namespace-wrapper

# Using yarn
yarn add @_koii/namespace-wrapper
```

### Prerequisites

- Node.js 16+ 
- TypeScript (recommended)
- Access to a Koii Network task node or local testing environment

## API Reference

### Core Classes and Methods

#### `NamespaceWrapper`
The primary class for interacting with Koii task infrastructure.

##### Key Methods

1. **Database Interactions**
   ```typescript
   // Store a key-value pair
   await namespaceWrapper.storeSet(key: string, value: string): Promise<void>

   // Retrieve a value by key
   await namespaceWrapper.storeGet(key: string): Promise<string | null>
   ```

2. **Cryptographic Utilities**
   ```typescript
   // Sign a payload
   await namespaceWrapper.payloadSigning(
     body: Record<string, unknown>, 
     privateKey?: Uint8Array
   ): Promise<string>

   // Verify signature
   await namespaceWrapper.verifySignature(
     signedMessage: string, 
     pubKey: string
   ): Promise<{ data?: string; error?: string }>
   ```

3. **Task State Management**
   ```typescript
   // Get current task state
   await namespaceWrapper.getTaskState(options: TaskStateOptions): Promise<TaskState>

   // Check submission and update round
   await namespaceWrapper.checkSubmissionAndUpdateRound(
     submissionValue?: string, 
     round: number
   ): Promise<void>
   ```

4. **Distribution Workflow**
   ```typescript
   // Upload distribution list
   await namespaceWrapper.uploadDistributionList(
     distributionList: Record<string, any>, 
     round: number
   ): Promise<boolean>

   // Validate and vote on distribution lists
   await namespaceWrapper.validateAndVoteOnDistributionList(
     validateDistribution: (submissionValue: string, round: number, nodePublicKey: string) => Promise<boolean>,
     round: number
   ): Promise<void>
   ```

### Logging

```typescript
// Log messages with different severity levels
await namespaceWrapper.logger(
  level: LogLevel,  // 'log' | 'warn' | 'error'
  message: string,
  action: string
): Promise<boolean>
```

## Repository Structure

- `src/`
  - `index.ts`: Main library implementation
  - `types.ts`: TypeScript type definitions
- `webasm_bincode_deserializer/`: WebAssembly and serialization utilities
- `package.json`: Project configuration and dependencies

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Create a Pull Request

### Running Tests

Currently, no specific test suite is configured. Contributions adding comprehensive tests are highly encouraged!

## License

This project is licensed under the ISC License. See the [LICENSE](LICENSE) file for details.

## Support

For support, please open an issue in the GitHub repository or join the [Koii Network Discord](https://discord.gg/koii).
