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
