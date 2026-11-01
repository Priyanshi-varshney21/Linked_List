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
        

