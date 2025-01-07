# Swap-Maximize

In a math challenge, Vikram was given two arrays, A and B, each containing N elements. His task was to maximize the difference between the sum of elements in array A (sumA) and the sum of elements in array B (sumB). The twist was that in each move, Vikram could swap any element from array A with any element from array B - they didn’t have to be at the same index. Now, Vikram must figure out the optimal way to maximize the value of sumA - sumB using these swaps. Can you help Vikram solve this puzzle?

Input
The first line of the input contains an integer N.
The second line of the input contains N space-separated integers of array A.
The third line of the input contains N space-separated integers of array B.

Constraints
1 ≤ N ≤ 105
1 ≤ Ai, Bi ≤ 109
Output
Print the maximum possible value of sumA - sumB possible after apply optimal moves.

def swap_and_maximize():
    # Input reading
    N = int(input())
    A = list(map(int, input().split()))
    B = list(map(int, input().split()))

    # Calculate initial sums
    sumA = sum(A)
    sumB = sum(B)

    # Sort A in ascending order and B in descending order
    A.sort()
    B.sort(reverse=True)

    # Perform swaps to maximize sumA - sumB
    for i in range(N):
        if A[i] < B[i]:
            # Calculate the impact of the swap
            sumA = sumA - A[i] + B[i]
            sumB = sumB - B[i] + A[i]

            # Swap elements
            A[i], B[i] = B[i], A[i]
        else:
            break

    # Output the result
    print(sumA - sumB)

# Call the function
swap_and_maximize()
