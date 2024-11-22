# Bloom Filters

A **Bloom Filter** is a space-efficient, probabilistic data structure used to test whether an element is a member of a set. It is particularly useful when memory is limited, and exact matches are not necessary. Bloom filters trade a small probability of false positives for a significant reduction in memory usage.

---

![bloomFilters](https://github.com/user-attachments/assets/6157189e-a6cd-4927-96f7-e83ce26df2e2)

## Key Features of Bloom Filters:

### Probabilistic Nature:
- Can confirm if an element **is not** in the set.
- Can return a **false positive**, meaning it may wrongly indicate an element is in the set.

### Space Efficiency:
- Uses much less memory compared to storing the entire set.

### No Deletion:
- Standard Bloom Filters do not support deleting elements without potential inaccuracies.

---

## How Bloom Filters Work:

A Bloom Filter is backed by a bit array of length \( m \), initially all set to 0, and \( k \) independent hash functions.

### Insertion:
1. When inserting an element, it is hashed using \( k \) different hash functions.
2. Each hash function generates an index in the bit array, and those indices are set to 1.

### Query (Membership Check):
1. To check if an element exists, it is hashed using the same \( k \) hash functions.
2. The indices from these hashes are checked in the bit array:
   - If **all bits** at the generated indices are 1, the element **might** be in the set.
   - If **any bit** is 0, the element is definitely **not** in the set.

---

## Properties:

### False Positives:
- Bloom Filters may indicate that an element exists even when it doesn’t. This happens because unrelated elements can set overlapping bits to 1.

### False Negatives:
- A Bloom Filter **never** reports false negatives; if it says an element is not present, it is guaranteed to be true.

### Hash Independence:
- The accuracy of a Bloom Filter depends on the independence of the hash functions.

---

## Advantages:
- **Space Efficiency**: Uses significantly less memory compared to storing the actual set.
- **Speed**: Both insertion and query operations are fast (\( O(k) \)), as they only involve hash computations and bit array updates.
- **Simplicity**: Easy to implement and integrate.

---

## Disadvantages:
- **False Positives**: Cannot always confirm an element’s membership.
- **No Deletions**: Once bits are set, they cannot be cleared without risking data integrity.
- **Scaling**: Adding elements increases the probability of false positives.

---

## Use Cases:

### Caching:
- To check if a resource is not cached before making a database or network call.

### Databases:
- Used in systems like **Apache Cassandra** and **Google Bigtable** to check for key existence before querying disks.

### Web Crawlers:
- To avoid revisiting previously seen URLs.

### Distributed Systems:
- To manage duplicate detection in systems like **blockchain** or **deduplication services**.


# Working of Bloom Filter

A Bloom Filter is a bit array of size \( m \), all initially set to `0`. The filter uses \( k \) hash functions to compute indices for the elements being added or checked.

---

## Insertion in Bloom Filter

When we want to add an item to the filter:
1. Calculate \( k \) hash values for the item using \( k \) independent hash functions: \( h_1(x), h_2(x), \ldots, h_k(x) \).
2. Set the bits at the calculated indices in the bit array to `1`.

### Example:
- Suppose we want to insert **"geeks"** into the filter.  
  \( m = 10 \) (size of bit array)  
  \( k = 3 \) (number of hash functions)
- Hash calculations:  
  \( h_1(\text{"geeks"}) \% 10 = 1 \)  
  \( h_2(\text{"geeks"}) \% 10 = 4 \)  
  \( h_3(\text{"geeks"}) \% 10 = 7 \)  
- Set the bits at indices \( 1, 4, \) and \( 7 \) to `1`.  

Bit array after adding **"geeks"**:  


- Now, we insert **"nerd"**:  
  \( h_1(\text{"nerd"}) \% 10 = 3 \)  
  \( h_2(\text{"nerd"}) \% 10 = 5 \)  
  \( h_3(\text{"nerd"}) \% 10 = 4 \)  
- Set the bits at indices \( 3, 5, \) and \( 4 \) to `1`.  

Bit array after adding **"nerd"**:  


---

## Query (Membership Check)

To check if an element is present in the filter:
1. Calculate \( k \) hash values for the item using \( k \) hash functions.
2. Check the bits at the calculated indices:
   - If **all bits** are set to `1`, the element **might** be present.
   - If **any bit** is `0`, the element is **definitely not** present.

### Example:
- To check for **"geeks"**:  
  \( h_1(\text{"geeks"}) \% 10 = 1 \)  
  \( h_2(\text{"geeks"}) \% 10 = 4 \)  
  \( h_3(\text{"geeks"}) \% 10 = 7 \)  
- Bits at indices \( 1, 4, \) and \( 7 \) are all `1`. Therefore, **"geeks"** might be present.

---

## False Positives in Bloom Filters

Bloom Filters are probabilistic, meaning they may return **false positives**. This happens when bits set by other elements overlap with those for the queried item.

### Example:
- Checking for **"cat"**:  
  \( h_1(\text{"cat"}) \% 10 = 1 \)  
  \( h_2(\text{"cat"}) \% 10 = 3 \)  
  \( h_3(\text{"cat"}) \% 10 = 7 \)  
- Bits at indices \( 1, 3, \) and \( 7 \) are all set to `1`, but **"cat"** was never added.  
- This is a **false positive** result.

---

## Reducing False Positives

False positives can be reduced by:
- Increasing the size of the bit array (\( m \)).
- Increasing the number of hash functions (\( k \)).

However, this comes at the cost of higher memory usage and slower operations.

---

## Operations Supported by a Bloom Filter:
- **Insert(x):** Insert an element into the Bloom Filter.
- **Lookup(x):** Check if an element is already present in the Bloom Filter (with a false-positive probability).

### Note:
- Bloom Filters do **not support deletion** of elements.

---

## Probability of False Positives

The probability of a false positive (\( P \)) can be calculated as:

\[
P = \left( 1 - \left[ 1 - \frac{1}{m} \right]^{kn} \right)^k
\]

Where:
- \( m \): Size of the bit array.
- \( k \): Number of hash functions.
- \( n \): Number of elements expected to be inserted.

---

## Size of Bit Array

If \( n \) (expected number of elements) and \( P \) (desired false positive probability) are known, the size of the bit array (\( m \)) can be calculated as:

\[
m = -\frac{n \ln P}{(\ln 2)^2}
\]

---

## Optimum Number of Hash Functions

The optimal number of hash functions (\( k \)) is given by:

\[
k = \frac{m}{n} \ln 2
\]

---

## Space Efficiency

Bloom Filters are highly space-efficient and are ideal for applications where memory is constrained, and false positives are tolerable.


