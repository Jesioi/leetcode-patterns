# Three Sum Reduction

Core Pattern:
fix one number
reduce remaining problem to Two Sum

Key Insight:
sort array first

Then:
for each i
solve Two Sum on remaining range

Invariant:
l and r search remaining space

Template:

Arrays.sort(nums);

for (int i = 0; i < nums.length; i++) {

    int l = i + 1;
    int r = nums.length - 1;

    while (l < r) {

    }

}

Signals:

- triplets
- quadruplets
- k-sum

Representative Problems:

- 3Sum
- 4Sum
