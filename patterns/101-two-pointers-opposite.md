# Opposite Direction Two Pointers

Core Pattern:
left pointer starts from beginning
right pointer starts from end

Key Insight:
use ordering / constraints
to eliminate search space

Invariant:
everything outside [l, r]
has already been processed

Template:

while (l < r) {

    if (condition) {
        l++;
    } else {
        r--;
    }

}

Signals:

- sorted array
- palindrome
- pair sum
- maximize/minimize area

Representative Problems:

- Valid Palindrome
- Two Sum II
- Container With Most Water
- Trapping Rain Water
