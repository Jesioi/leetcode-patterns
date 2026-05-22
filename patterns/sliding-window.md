# Sliding Window

Core Pattern:
expand right pointer
shrink left pointer when invalid

Invariant:
window always satisfies condition

Template:

for (int r = 0; r < nums.length; r++) {

    // add nums[r]

    while (window invalid) {

        // remove nums[l]
        l++;
    }

    // update answer

}

Signals:

- longest substring
- contiguous subarray
- at most K
- minimum window
- running window

Representative Problems:

- Longest Substring Without Repeating Characters
- Permutation in String
- Minimum Window Substring
- Best Time to Buy and Sell Stock
