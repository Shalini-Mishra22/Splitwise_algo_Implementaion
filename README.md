# Splitwise_algo_Implementaion
The Splitwise Algorithm implemented in this project calculates the minimum number of transactions required to settle debts among a group of individuals. Here's how it works:

1. Input Handling: 
   - It starts by taking input for the number of transactions and the number of individuals (friends).
   - Each transaction specifies an amount that one person owes to another.

2. Net Balance Calculation:
   - It maintains a `net` map where each person's net balance (total amount they owe or are owed) is stored.
   - For each transaction, it updates the net balance:
     - If person X gives an amount 'amt' to person Y, it decreases X's net balance by 'amt' and increases Y's net balance by 'amt'.

3. Sorting by Net Balance:
   - It uses a multiset (`m`) sorted by net balances, where each entry is a pair of (person, net balance).
   - Only individuals with non-zero net balances are included in `m`.

4. Settlement Process:
   - It repeatedly selects the person who owes the most (debit_person) and the person who is owed the most (credit_person) from the sorted multiset `m`.
   - It settles the debt by transferring the minimum of what the debtor owes and what the creditor is owed.
   - This process continues until all debts are settled (i.e., the multiset `m` becomes empty).

5. Output:
   - For each transaction, it prints out who pays whom and how much until all debts are settled.
   - Finally, it prints the total number of transactions required to settle all debts.

This algorithm ensures that debts are settled optimally with the minimum number of transactions, leveraging efficient data structures for quick access and modification of net balances. It demonstrates effective use of maps, multisets, and algorithmic thinking in financial settlement scenarios.

Time complexity-
 The overall time complexity of the Splitwise Algorithm is O(T + N log N), where T is the number of transactions and N is the number of individuals (friends).
