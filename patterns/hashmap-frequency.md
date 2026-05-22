# HashMap Frequency / Lookup

Core Pattern:
store previously seen information

Key Insight:
trade memory for O(1) lookup

Common Structures:
value -> frequency
value -> index
char -> count

Template:

Map<Integer, Integer> map = new HashMap<>();

for (int x : nums) {
map.put(x, map.getOrDefault(x, 0) + 1);
}

Signals:

- duplicate
- frequency
- complement
- counting
- previously seen

Representative Problems:

- Two Sum
- Contains Duplicate
- Valid Anagram
- Top K Frequent Elements
