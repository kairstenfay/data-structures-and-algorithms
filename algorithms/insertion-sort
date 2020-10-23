#!/usr/bin/env python3
#
# An implementation of insertion sort in python where the input is a list of
# integers.
#
from typing import List


def insertion_sort(array: List[int]) -> List[int]:
    """
    >>> insertion_sort([1,2,3])
    [1, 2, 3]

    >>> insertion_sort([99])
    [99]

    >>> insertion_sort([])
    []

    >>> insertion_sort([4,3,2,1])
    [1, 2, 3, 4]

    >>> insertion_sort([5,42,1,0,99])
    [0, 1, 5, 42, 99]
    """
    i = 0
    while i < len(array):
        j = i
        while j > 0 and array[j - 1] > array[j]:
            # swap
            temp = array[j]
            array[j] = array[j - 1]
            array[j - 1] = temp
            j -= 1
        i += 1
    return array


if __name__ == "__main__":
    import doctest
    doctest.testmod()
