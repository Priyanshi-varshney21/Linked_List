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
