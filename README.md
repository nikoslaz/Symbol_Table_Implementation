# Symbol Table Implementation

## Overview
A C implementation of a symbol table (hash map) with two versions:
1. **Hash Table** implementation (`symtablehash.c`)
2. **Linked List** implementation (`symtablelist.c`)

## Features

### Core Operations
| Function | Description | Complexity |
|----------|-------------|------------|
| `SymTable_new()` | Creates new symbol table | O(1) |
| `SymTable_free()` | Frees all memory | O(n) |
| `SymTable_getLength()` | Returns number of bindings | O(1) |
| `SymTable_put()` | Adds/updates key-value pair | O(1) avg / O(n) worst |
| `SymTable_remove()` | Removes key-value pair | O(1) avg / O(n) worst |
| `SymTable_contains()` | Checks if key exists | O(1) avg / O(n) worst |
| `SymTable_get()` | Retrieves value by key | O(1) avg / O(n) worst |
| `SymTable_map()` | Applies function to all bindings | O(n) |

## Key Features

### Automatic Resizing (Hash version only):
- Grows when load factor exceeds threshold
- Uses prime number bucket sizes for better distribution

### Memory Management:
- Properly frees all allocated memory
- Uses `strdup` for key copying

### Error Handling:
- Assertions validate input parameters
- Returns `NULL`/`0` on failure

### Polymorphic Values:
- Stores `void*` values for flexibility
- Supports any data type

## Build and Run

```bash
make

# Run program
./symbol_table
```
