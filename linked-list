#!/usr/bin/env python3
#
# An implementation of a singly linked list in python where the value of each
# node is an integer.
#
class ListNode:
    def __init__(self, value: int, next=None):
        self.value = value
        self.next = next

    def __str__(self) -> str:
        return f"({self.value})"

    def __repr__(self) -> str:
        return self.__str__()


class LinkedList:
    def __init__(self, head: ListNode=None):
        self.head = head

    def __repr__(self) -> str:
        """
        >>> ll = LinkedList()
        >>> print(ll)
        <BLANKLINE>

        >>> ll.push(ListNode(2))
        >>> print(ll)
        (2)→

        >>> ll.push(ListNode(3))
        >>> print(ll)
        (2)→(3)→
        """
        string = ""
        current = self.head
        while current:
            string += str(current) + "→"
            current = current.next
        return string

    def length(self) -> int:
        """
        Returns the number of nodes in the LinkedList.

        >>> ll = LinkedList(ListNode(3))
        >>> ll.length()
        1

        >>> ll.push(ListNode(4))
        >>> ll.length()
        2

        >>> LinkedList().length()
        0
        """
        length = 0
        current = self.head
        while current:
            length += 1
            current = current.next
        return length

    def push(self, node: ListNode):
        """
        >>> ll = LinkedList(ListNode(3))
        >>> ll.length()
        1

        >>> ll.push(ListNode(2))
        >>> ll.length()
        2

        >>> ll.push(ListNode(3))
        >>> ll.length()
        3
        """
        current = self.head
        if current is None:
            self.head = node
        else:
            while current and current.next:
                current = current.next
            current.next = node

    def pop(self) -> ListNode:
        """
        Raises an :class:`IndexError` if the LinkedList is empty.

        >>> ll = LinkedList()
        >>> ll.pop()
        Traceback (most recent call last):
        ...
        IndexError: pop from empty LinkedList

        >>> ll2 = LinkedList(ListNode(1))
        >>> ll2.push(ListNode(2))
        >>> ll2.push(ListNode(3))
        >>> ll2.pop()
        (3)
        >>> ll2.pop()
        (2)
        >>> ll2.pop()
        (1)
        """
        current = self.head
        if current is None:
            raise IndexError("pop from empty LinkedList")

        if current.next is None:
            self.head = None
            return current

        while current and current.next and current.next.next:
            current = current.next
        temp = current.next
        current.next = None
        return temp

    def insert(self, index: int, node: ListNode):
        """
        >>> ll = LinkedList()
        >>> ll.insert(10, ListNode(1))
        >>> print(ll)
        (1)→

        >>> ll.insert(0, ListNode(3))
        >>> print(ll)
        (3)→(1)→
        """
        if index == 0:
            temp = self.head
            self.head = node
            self.head.next = temp
            return

        current = self.head
        if current is None:
            self.head = node
        else:
            steps_taken = 0
            while current and current.next:
                if steps_taken == index - 1:
                    temp = current.next
                    current.next = node
                    current.next.next = temp
                    return
                else:
                    current = current.next
                    steps_taken += 1
            current.next = node

    def remove(self, value: int):
        """
        Raises a :class:`ValueError` if the given *value* is not in the
        LinkedList.

        >>> ll = LinkedList()
        >>> ll.remove(1)
        Traceback (most recent call last):
        ...
        ValueError: LinkedList.remove(x): x not in LinkedList

        >>> ll.push(ListNode(1))
        >>> ll.remove(1)
        >>> print(ll)
        <BLANKLINE>

        >>> ll.push(ListNode(1))
        >>> ll.push(ListNode(2))
        >>> ll.push(ListNode(1))
        >>> ll.remove(1)
        >>> print(ll)
        (2)→(1)→

        >>> ll.push(ListNode(3))
        >>> ll.push(ListNode(4))
        >>> ll.remove(4)
        >>> print(ll)
        (2)→(1)→(3)→
        """
        current = self.head
        if current and current.value == value:
            self.head = current.next
            return

        while current and current.next:
            if current.next.value == value:
                current.next = current.next.next
                return
            current = current.next
        raise ValueError("LinkedList.remove(x): x not in LinkedList")

    def index(self, value: int) -> int:
        """
        Returns the first index at which the given *value* is found.

        >>> ll = LinkedList()
        >>> ll.index(1)
        -1

        >>> ll.push(ListNode(2))
        >>> ll.push(ListNode(3))
        >>> ll.index(3)
        1

        >>> ll.push(ListNode(3))
        >>> ll.index(3)
        1
        """
        current = self.head
        index = 0
        while current:
            if current.value == value:
                return index
            current = current.next
            index += 1

        return -1

    def count(self, value: int) -> int:
        """
        Returns the number of time sthe given *value* appears.

        >>> ll = LinkedList()
        >>> ll.count(3)
        0

        >>> ll.push(ListNode(2))
        >>> ll.push(ListNode(3))
        >>> ll.count(3)
        1

        >>> ll.push(ListNode(3))
        >>> ll.count(3)
        2
        """
        count = 0
        current = self.head

        while current:
            if current.value == value:
                count += 1
            current = current.next

        return count

    def reverse(self):
        """
        Reverse the nodes in a LinkedList.

        >>> ll = LinkedList()
        >>> ll.reverse()

        >>> ll.push(ListNode(2))
        >>> ll.reverse()
        >>> print(ll)
        (2)→

        >>> ll.push(ListNode(3))
        >>> ll.reverse()
        >>> print(ll)
        (3)→(2)→
        """
        current = self.head
        if current is None or current.next is None:
            return

        prev = None

        while current and current.next:
            temp = current.next
            current.next = prev
            prev = current
            current = temp

        current.next = prev
        self.head = current


if __name__ == "__main__":
    import doctest
    doctest.testmod()
