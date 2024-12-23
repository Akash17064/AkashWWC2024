#include <iostream>
#include <vector>
// Definition for singly-linked list.
struct ListNode {
    int val;
    ListNode *next;
    ListNode() : val(0), next(nullptr) {}
    ListNode(int x) : val(x), next(nullptr) {}
    ListNode(int x, ListNode *next) : val(x), next(next) {}
};

class Solution {
public:
    ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {
        ListNode* dummy = new ListNode(); // Dummy node to simplify list operations
        ListNode* current = dummy;       // Pointer to build the result list
        int carry = 0;                   // To store carry from each addition step

        while (l1 != nullptr || l2 != nullptr || carry != 0) {
            int sum = carry;
            if (l1 != nullptr) {
                sum += l1->val;
                l1 = l1->next;
            }
            if (l2 != nullptr) {
                sum += l2->val;
                l2 = l2->next;
            }

            carry = sum / 10; // Calculate carry for the next step
            current->next = new ListNode(sum % 10); // Create new node with the current digit
            current = current->next;               // Move to the next node
        }

        return dummy->next; // Return the next node of the dummy (head of the result list)
    }
};

// Utility function to print a linked list
void printList(ListNode* head) {
    while (head != nullptr) {
        std::cout << head->val;
        if (head->next != nullptr) std::cout << " -> ";
        head = head->next;
    }
    std::cout << std::endl;
}

// Helper function to create a linked list from a vector
ListNode* createList(const std::vector<int>& nums) {
    ListNode* dummy = new ListNode();
    ListNode* current = dummy;
    for (int num : nums) {
        current->next = new ListNode(num);
        current = current->next;
    }
    return dummy->next;
}

int main() {
    // Example usage
    std::vector<int> num1 = {2, 4, 3}; // 342
    std::vector<int> num2 = {5, 6, 4}; // 465

    ListNode* l1 = createList(num1);
    ListNode* l2 = createList(num2);

    Solution solution;
    ListNode* result = solution.addTwoNumbers(l1, l2);

    printList(result); // Output: 7 -> 0 -> 8 (807)

    return 0;
}
