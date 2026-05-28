# Prefix Sum

Core Invariant:
prefix[i] stores sum before index i

Key Insight:
subarray sum can be computed in O(1)

Formula:
sum(l...r) =
prefix[r + 1] - prefix[l]

Template:

prefix[0] = 0;

for (int i = 0; i < nums.length; i++) {
prefix[i + 1] = prefix[i] + nums[i];
}

Signals:

- subarray sum
- cumulative sum
- range sum
- sum between indices

Representative Problems:

- Subarray Sum Equals K
- Range Sum Query
- Continuous Subarray Sum
