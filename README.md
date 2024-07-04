# @cch137/random

The `@cch137/random` package provides a powerful and flexible random number generator with multiple algorithms and useful utilities for generating random values. This package is suitable for both browser and Node.js environments.

## Installation

```bash
npm install @cch137/random
```

## Usage

The `@cch137/random` package offers a `Random` class with various methods to generate random numbers, strings, and perform other random-related operations.

### Example

```typescript
import random, { Random, MT, LCG } from "@cch137/random";

// Using the default instance
console.log(random.random()); // Random number between 0 and 1
console.log(random.randint(1, 10)); // Random integer between 1 and 10
console.log(random.choice([1, 2, 3, 4, 5])); // Random choice from an array
console.log(random.base64(16)); // Random base64 string of length 16

// Creating a custom instance with a seed
const seededRandom = new Random(12345);
console.log(seededRandom.random()); // Random number between 0 and 1 with seed 12345

// Using a different core algorithm
const lcgRandom = new Random(LCG(98765));
console.log(lcgRandom.random()); // Random number between 0 and 1 with LCG algorithm
```

## Features

- **Multiple Algorithms**: Supports Mersenne Twister (default) and Linear Congruential Generator (LCG).
- **Random Number Generation**: Generate random numbers, integers, and perform random selections from arrays.
- **Random String Generation**: Generate random strings in various formats (base10, base16, base64, base64url).
- **Seeding**: Create reproducible random sequences by initializing with a seed.

### Methods

- **`random(start?: number, end?: number): number`**: Returns a random number between `start` (inclusive) and `end` (exclusive). Defaults to 0 and 1 if not provided.
- **`randint(start: number, end: number): number`**: Returns a random integer between `start` (inclusive) and `end` (exclusive).
- **`choice<T>(array: T[]): T`**: Returns a random element from an array.
- **`choices<T>(array: T[], k?: number): T[]`**: Returns an array of `k` random elements from the input array.
- **`sample<T>(array: T[], k?: number): T[]`**: Returns a random sample of `k` elements from the input array without replacement.
- **`shuffle<T>(array: T[]): T[]`**: Returns a new array with elements shuffled.
- **`base10(len?: number): string`**: Returns a random base10 string of specified length.
- **`base16(len?: number): string`**: Returns a random base16 string of specified length.
- **`base64(len?: number): string`**: Returns a random base64 string of specified length.
- **`base64url(len?: number): string`**: Returns a random base64url string of specified length.
