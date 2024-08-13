# HashTable Implementation in TypeScript

This project is a practical exploration of hash tables using TypeScript. A hash table is a data structure that allows for efficient data retrieval using key-value pairs. Hash tables are widely used in scenarios where quick data lookup is essential, such as in implementing associative arrays, managing caches, and creating databases.

## How It Works

In this implementation, each key is passed through a hash function that generates an index, where the corresponding value is stored in an array. This ensures efficient storage and retrieval of data.

### Code Example

Here’s a basic implementation of a hash table in TypeScript:

```typescript
class HashTable {
    private table: { [key: string]: any } = {};

    // Simple hash function to generate an index from a key
    private hash(key: string): string {
        let hash = 0;
        for (let i = 0; i < key.length; i++) {
            hash += key.charCodeAt(i);
        }
        return hash.toString();
    }

    // Method to set a key-value pair in the hash table
    set(key: string, value: any): void {
        const hashedKey = this.hash(key);
        this.table[hashedKey] = value;
    }

    // Method to retrieve a value by key from the hash table
    get(key: string): any {
        const hashedKey = this.hash(key);
        return this.table[hashedKey];
    }

    // Method to remove a key-value pair from the hash table
    remove(key: string): void {
        const hashedKey = this.hash(key);
        delete this.table[hashedKey];
    }
}
