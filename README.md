# Implementing-the-Rabin-Karp-algorithm-in-Java
The RabinKarp method takes two strings, a pattern and a text, as arguments and returns a list of all occurrences of the pattern in the text. Here we assume that the length of the text is no less than the length of the pattern.

Now let's go through each step of the algorithm in detail.

In this implementation, we use a method charToLong to associate each symbol with some number. For example, for upper-case letters, it returns the sequence number of a letter in the alphabet, for lower-case letters it returns the sequence number plus 32.
Recall that for the Rabin-Karp algorithm we need to choose constants aa and mm. In this implementation, the constants are equal 5353 and 10^9 + 910 
9
 +9 respectively.
First, we need to calculate a hash value for the pattern and for the first substring of the text using the formula of the polynomial hash directly. We perform it simultaneously in the for loop. Also, we store the current power of aa in a variable pow. After the last multiplication, it is equal to a^{|p| - 1}a 
∣p∣−1
  and the value will be used in further computations.
Here we create a list to store occurrences of the pattern. Then, we move along the text from the right to the left calculating and comparing the hash values of the pattern and the current substring. If they are equal, we perform a symbol-by-symbol comparison. If the strings are indeed equal, we add the index of the current substring to the list of all occurrences. At the end of the for loop, we update the hash value for the current substring. After the loop is finished, we return the list of all occurrences as a final result.
Note that when calculating a hash value for the next substring (comment 5) we add mm to the difference. Since a hash value for the pattern is a non-negative number, hash values for all substrings should be non-negative as well. This addition is done to avoid the processing of negative values.
