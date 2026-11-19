# Linked_List
# TRAVERSAL LINKED LISTS
def LLTraversal(self, head):
        ans=[]
        if head is None:
            return 
        else:
            curr=head
            while curr is not None:
                ans.append(curr.data)
                curr=curr.next
        return ans

# DELETE HEAD
def deleteHead(self, head):
        if head is None:
            return 
        else:
            head=head.next
            return head

# DELETE TAIL NODE
 def deleteTail(self, head):
        if head is None or head.next is None:
            return
        else:
            curr=head
            while curr.next.next is not None:
                curr=curr.next
            temp=curr.next
            curr.next=None
            del temp
            return head

# DELETION OF KTH NODE
def deleteKthNode(self, head, k):
        if head is None:
            return
        if k==1:
            head=head.next
            return head
        curr=head
        for i in range(1,k-1):
            curr=curr.next
        if curr is None and curr.next is None:
            return head
        temp=curr.next
        curr.next=curr.next.next
        del temp
        return head

# DELETE THE ELEMENT WITH VALUE X
def deleteNodeWithValueX(self, head, X):
        if head is None:
            return 
        if head.data==X:
            return head.next
        curr=head
        while curr.next is not None:
            if curr.next.data==X:
                curr.next=curr.next.next
                break
            curr=curr.next
        return head


# INSERTION AT THE HEAD OF THE LINKED LIST
 def insertAtHead(self, head, X):
        if head is None:
            head=ListNode(X)          #CREATE A NEW NODE
            return head
        else:
            curr=head
            prev=ListNode(X)
            prev.next=curr
            head=prev
        return head

# INSERTION AT THE TAIL OF THE LINKED LIST
def insertAtTail(self, head, X):
        if head is None:
            head=ListNode(X)
            return head
        curr=head
        while curr.next is not None:
            curr=curr.next
        curr.next=ListNode(X)
        return head

# INSERTION AT THE KTH POSITION OF THE LINKED LIST
def insertAtKthPosition(self, head, X, k):
        if k==1:
            newnode=ListNode(X)
            newnode.next=head
            return newnode
        curr=head
        for i in range(1,k-1):
            curr=curr.next
        newnode=ListNode(X)
        newnode.next=curr.next
        curr.next=newnode
        return head

# INSERTION BEFORE THE VALUE X IN A LINKED LIST
def insertBeforeX(self, head, X, val):
        newNode=ListNode(val)
        if head is None:
            return 
        if head.data==X:
            newNode.next=head
            return newNode
        curr=head
        while curr.next is not None:
            if curr.next.data==X:
                newNode.next=curr.next
                curr.next=newNode
                return head
            curr=curr.next
        return head

# FIND THE LENGTH OF THE LINKED LIST
def getLength(self, head):
        count=0
        if head is None:
            return 0
        curr=head
        while curr is not None:
            count+=1
            curr=curr.next
        return count
        
# SEARCH IN A LINKED LIST
def searchKey(self, head, key):
        curr=head
        while curr.data is not None:
            if curr.data==X:
                return True
            curr=currr.next
        return False

# FIND THE MIDDLE OF A LINKED LIST
def middleOfLinkedList(self, head):
        if head is None:
            return 
        slow=head
        fast=head
        while fast is not None and fast.next is not None:
            slow=slow.next
            fast=fast.next.next
        return slow

# DELETE THE MIDDLE NODE
def deleteMiddle(self, head):
        if head is None:
            return 
        prev=None
        slow=head
        fast=head
        while fast is not None and fast.next is not None:
            prev=slow
            slow=slow.next
            fast=fast.next.next
        prev.next=slow.next
        return head

# CHECK IF THE LINKED LIST IS PALINDROME
def isPalindrome(self, head):
        if head is None or head.next is None:
            return True
        #Find middle
        slow=head
        fast=head
        while fast.next and fast.next.next:
            slow=slow.next
            fast=fast.next.next
        #Reverse the second half
        second=self.reverse(slow.next)
        #Compare both halves
        first=head
        while second:
            if first.val!=second.val:
                return False
            first=first.next
            second=second.next
        return True
        #Reverse
    def reverse(self,head):
        prev=None
        curr=head
        while curr:
            next=curr.next
            curr.next=prev
            prev=curr
            curr=next
        return prev

# DETECT A CYCLE
def hasCycle(self, head):
        slow=head
        fast=head
        while fast and fast.next:
            slow=slow.next
            fast=fast.next.next
            if slow==fast:
                return True
        return False

# FIND THE STARTING POINT
def findStartingPoint(self, head):
        slow=head
        fast=head
        while fast and fast.next:
            slow=slow.next
            fast=fast.next.next
            if slow==fast:
                break
        else:
            return None
        slow=head
        while slow!=fast:
            slow=slow.next
            fast=fast.next
        return slow

# COUNT LENGTH OF A LOOP
def findLengthOfLoop(self, head):
        slow=head
        fast=head
        while fast and fast.next:
            slow=slow.next
            fast=fast.next.next
            if slow==fast:
                return self.count(slow)
        return 0
    def count(self,node):
        count=1
        temp=node.next
        while temp!=node:
            count+=1
            temp=temp.next
        return count

# FIND THE INTERSECTION POINT OF Y LL
def getIntersectionNode(self, headA, headB):
        p1=headA
        p2=headB
        while p1!=p2:
            if p1 is None:
                p1=headB
            else:
                p1=p1.next
            if p2 is None:
                p2=headA
            else:
                p2=p2.next
        return p2

#  Reverse LL in group of given size K
def reverseKGroup(self, head, k):
    if head is None or k == 1:
        return head

    curr = head
    prev = None
    count = 0

    # Reverse first k nodes
    while curr and count < k:
        nextNode = curr.next
        curr.next = prev
        prev = curr
        curr = nextNode
        count += 1

    # Connect remaining groups
    if curr:
        head.next = self.reverseKGroup(curr, k)

    return prev

# MERGE TWO SORTED LISTS
def mergeTwoLists(self, list1, list2):
        if list1 is None:
            return list2
        if list2 is None:
            return list1
        if list1.val<=list2.val:
            list1.next=self.mergeTwoLists(list1.next,list2)
            return list1
        else:
            list2.next=self.mergeTwoLists(list1,list2.next)
            return list2


# SORT A LINKED LISTS
def sortList(self, head):
        if head is None or head.next is None:
            return head
        slow=head
        fast=head
        prev=None
        while fast and fast.next:
            prev=slow
            slow=slow.next
            fast=fast.next.next
        prev.next=None
        left=self.sortList(head)
        right=self.sortList(slow)
        return self.mergeTwoLists(left,right)
    def mergeTwoLists(self, list1, list2):
        if list1 is None:
            return list2
        if list2 is None:
            return list1
        if list1.val<=list2.val:
            list1.next=self.mergeTwoLists(list1.next,list2)
            return list1
        else:
            list2.next=self.mergeTwoLists(list1,list2.next)
            return list2

# FLATTEN THE LINKED LIST
def flattenLinkedList(self, head):
        if head is None or head.next is None:
            return head
        head.next=self.flattenLinkedList(head.next)
        head=self.merge(head,head.next)
        return head
    def merge(self,a,b):
        if a is None:
            return 
        if b is None:
            return a
        if a.data<=b.data:
            result=a
            result.bottom=self.merge(a.bottom,b)
        else:
            result=b
            result.bottom=self.merge(a,b.bottom)
        result.next=None
        return result

# REVESRE THE LINKED LIST OF SIZE K
def reverseKGroup(self, head, k):
        if head is None:
            return None
        curr=head
        prev=None
        count=0
        while curr and count<k:
            front=curr.next
            curr.next=prev
            prev=curr
            curr=front
            count+=1
        if curr:
            head.next=self.reverseKGroup(curr,k)
        return prev

# ROTATE LINKED LIST
if head is None or head.next is None:
        return head

    curr = head
    length = 1

    while curr.next:
        curr = curr.next
        length += 1

    curr.next = head

    k = k % length

    steps = length - k

    curr = head
    for i in range(steps - 1):
        curr = curr.next

    newHead = curr.next
    curr.next = None

    return newHead
