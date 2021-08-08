# Binary-Search-Trees
the structure of data affects performance, especially when it comes to the time required to find an element in a large data store. As part of that we will discover a new self-referential form of data, the binary search tree or BST.


    import colorama
    from colorama import Fore

    class Node:
        def __init__(self, data):
            self.data= data
            self.next= None
            self.prev= None


        def value(self):
            return (self.data)

    class Tree:
        def __init__(self):
            self.root= None #initializing with none value

        def add(self, NodeVal):
            NewNode= Node(NodeVal)


            #funtion if value is to the left of head root
            def left(NewNode, root):

                if root.prev is None: #will add node when node to the legt is empty
                    root.prev = NewNode
                    return

                if NewNode.value() == root.prev.value():

                    return (f'Node {NodeVal} already exists in the tree')

                newRoot= root.prev
                if NewNode.value() > newRoot.value():
                    right(NewNode, newRoot)


                if NewNode.value() < newRoot.value():
                    left(NewNode, newRoot)



            #funtion if value is to the right of head root
            def right(NewNode, root):

                if root.next is None:
                    root.next = NewNode
                    return

                if NewNode.value() == root.next.value():

                    return (f'Node {NodeVal} already exists in the tree')

                newRoot= root.next
                if NewNode.value() > newRoot.value():
                    right(NewNode, newRoot)


                if NewNode.value() < newRoot.value():
                    left(NewNode, newRoot)


            #if the Tree is empty
            if self.root is None:
                self.root = NewNode
                return

            #if the value given exists in the tree
            if NewNode.value() == self.root.value():
                #print(f'Node {NodeVal} already exists in the tree')
                return (f'Node {NodeVal} already exists in the tree')


            #left case   
            if NewNode.value() < self.root.value():
                left(NewNode, self.root)

            #right case
            if NewNode.value() > self.root.value():
                right(NewNode, self.root)



    if True:

        testcases= Tree()

        #test 1
        testcases.add(10)
        if testcases.root.value() == 10:
            print(f'{Fore.GREEN}Test 1 passed!')
        else: 
            print(f'{Fore.RED}Test 1 failed!')

        #test 2

        if testcases.root.next is None:
            testcases.add(10)

            if testcases.root.next is None:
                print(f'{Fore.GREEN}Test 2 passed!')
            else:
                 print(f'{Fore.RED}Test 2 failed!')
        #test 3

        testcases.add(15)
        if testcases.root.next.value() is 15:
            print(f'{Fore.GREEN}Test 3 passed!')
        else:
            print(f'{Fore.RED}Test 3 failed!')

        #test 4

        testcases.add(15)

        if testcases.root.next.value() is 15 and testcases.root.next.next is None and testcases.root.next.prev is None:
            print(f'{Fore.GREEN}Test 4 passed!')
        else: 
            print(f'{Fore.RED}Test 4 failed!')


        #test 5
        testcases.add(5)

        if testcases.root.prev.value() is 5:
            print(f'{Fore.GREEN}Test 5 passed!')
        else:
            print(f'{Fore.RED}Test 5 failed!')

        #test 6

        testcases.add(5)
        if testcases.root.prev.value() is 5 and testcases.root.prev.next is None and testcases.root.prev.prev is None:
            print(f'{Fore.GREEN}Test 6 passed!')
        else: 
            print(f'{Fore.RED}Test 6 failed!')

        #test 7

        testcases.add(12.5)

        if testcases.root.next.prev.value() is 12.5:
            print(f'{Fore.GREEN}Test 7 passed!')
        else:
            print(f'{Fore.RED}Test 7 failed!')


        #test 8

        testcases.add(12.5)

        if testcases.root.next.value() is 15 and testcases.root.next.next is None and testcases.root.next.prev.value() is 12.5:
            print(f'{Fore.GREEN}Test 8 passed!')
        else:
            print(f'{Fore.RED}Test 8 failed!')

        #test 9

        testcases.add(17.5)

        if testcases.root.next.next.value() is 17.5:
            print(f'{Fore.GREEN}Test 9 passed!')
        else:
            print(f'{Fore.RED}Test 9 failed!')

        #test 10
        testcases.add(17.5)

        if testcases.root.next.value() is 15 and testcases.root.next.next.value() is 17.5  and testcases.root.next.prev.value() is 12.5:
            print(f'{Fore.GREEN}Test 10 passed!')
        else:
            print(f'{Fore.RED}Test 10 failed!')

        #test 11
        testcases.add(16)
        if testcases.root.next.next.prev.value() is 16:
            print(f'{Fore.GREEN}Test 11 passed!')
        else:
            print(f'{Fore.RED}Test 11 failed!')

        #test 12
        testcases.add(18)
        if testcases.root.next.next.next.value() is 18:
            print(f'{Fore.GREEN}Test 12 passed!')
        else:
            print(f'{Fore.RED}Test 12 failed!')


        #test 13
        testcases.add(16)
        testcases.add(18)

        if testcases.root.next.next.value() is 17.5 and testcases.root.next.next.prev.value() is 16  and testcases.root.next.next.next.value() is 18:
            print(f'{Fore.GREEN}Test 13 passed!')
        else:
            print(f'{Fore.RED}Test 13 failed!')

        #test 14

        testcases.add(7.5)

        if testcases.root.prev.next.value() is 7.5:
            print(f'{Fore.GREEN}Test 14 passed!')
        else:
            print(f'{Fore.RED}Test 14 failed!')

        #test 15

        testcases.add(2.5)

        if testcases.root.prev.prev.value() is 2.5:
            print(f'{Fore.GREEN}Test 15 passed!')
        else:
            print(f'{Fore.RED}Test 15 failed!')

        #test 16

        testcases.add(7.5)
        testcases.add(2.5)

        if testcases.root.prev.value() is 5 and testcases.root.prev.next.value() is 7.5  and testcases.root.prev.prev.value() is 2.5:
            print(f'{Fore.GREEN}Test 16 passed!')
        else:
            print(f'{Fore.RED}Test 16 failed!')

