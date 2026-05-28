# Trie

Core Pattern:
Prefix tree for string traversal

Core Insight:
Shared prefixes reuse the same traversal path.

Core Components:

- TrieNode
- children array/map
- isWord flag
- character traversal

Common Operations:

- insert
- search
- startsWith

Template Signal:

- prefix matching
- autocomplete
- dictionary lookup
- word search
- prefix queries

Key Question:
Am I matching a complete word or just a prefix?

Common Bugs:

- forgetting isWord
- incorrect character indexing
- creating duplicate nodes
- confusing prefix with full word

Representative Problems:

- Implement Trie
- Design Add and Search Words Data Structure
- Word Search II
