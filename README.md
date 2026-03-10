# DAA

class Solution {
public:
    ListNode* partition(ListNode* head, int x) {
        ListNode *low = new ListNode(0);
        ListNode *high = new ListNode(0);
        
        ListNode *duml = low;
        ListNode *dumg = high;

        while(head){
            if(head->val < x){
                duml -> next = head;
                duml = duml -> next;
            }else{
                dumg -> next = head;
                dumg = dumg -> next;
            }
            head = head->next;
        }

        duml->next = high->next;
        dumg->next = NULL;

        return low -> next;
    }
};
