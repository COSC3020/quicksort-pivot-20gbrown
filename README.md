[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-718a45dd9cf7e7f842a935f5ebbe5719a5e09af4491e668f4dbf3b35d5cca122.svg)](https://classroom.github.com/online_ide?assignment_repo_id=12441339&assignment_repo_type=AssignmentRepo)
# Quicksort Pivots

in the lectures I only briefly mentioned strategies for determining a good pivot
for quicksort. The implementation on the slides simply picks the leftmost
element in the part of the array that we consider as a pivot. I also mentioned a
few other ways of picking a good pivot, e.g. randomly.

Median-of-three is also a good way of picking a pivot -- inspect the first,
middle, and last elements of the part of the array under consideration and
choose the median value. Using the probabilities for picking a pivot in a
particular part of the array (in the same way as we did on slide 34), argue
whether this method is more or less (or equally) likely to pick a good pivot
compared to simply choosing the first element. Assume that all permutations are
equally likely, i.e. the input array is ordered randomly.

Your answer must derive probabilities for choosing a good pivot and
quantitatively reason with them.

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

# Answer
Median-of-three:
1. On an average input, our chosen pivot is equally likely to be the $i^th$ smallest for any i = 1, 2, ... , n.
2. With probability 1/2, our pivot will be from the middle $n$/2 elements – a good pivot.
3. Any good pivot creates two partitions of size at most $3n/4$.
4. We expect to pick one good pivot every two tries.
5. Expected number of splits is at most 2 log<sub>(4/3)</sub> n ∈ Θ(log n).
6. Θ($n$ log $n$) total comparisons.

First element:
1. On an average input (i.e., a random order of n items), our chosen pivot is equally likely to be the ith smallest for any i = 1, 2, ..., n.
2. With probability 1/n, our pivot will be the first element – a pivot that may not be as balanced as other methods.
3. A pivot from the first element can create partitions of various sizes, depending on the input data.
4. The probability of choosing a pivot that creates balanced partitions is lower compared to methods like median-of-three.
5. Expected number of splits is determined by the distribution of the data, and it can be highly variable.
6. The overall performance of quicksort with a first element pivot may vary depending on the input data and its distribution.

Chossing the first element or doing the median-of-three method do not have the same probability. The median-of-three method has a much better probabilty of selecting a good pivot because selecting the first element is highly dependent on a small input size. 

