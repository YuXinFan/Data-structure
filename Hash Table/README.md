## Background

In this last episode of the Mafghanistan trilogy, after a quagmire decisive victory,

the Mamerican forces planned to occupy peace keep in Mafghanistan for the next 100 year.

To monitor terrorist activities, the Commanding General of the Mamerican forces wanted

to wiretap on all Internet communications to detect words that are used at abnormal frequencies,

excluding stop words.

## Data structures

Create a hash table where a key is a word and its value is the word's frequency in a word file.

Exclude stop words from the hash table.

* Each entry in the table is a linked list of nodes where the keys in all the nodes
 
  have the same hash code.

* Insert a new key at the beginning of the corresponding linked list. All the keys

  in the hash table must be unique.

* When deleting a key, do not change the order of all the other nodes in the linked list.

* The hash table has an initial length and a load factor, both of which are integers

  and are provided by the first line of the input. Let size be the total number of keys

  in the hash table. After inserting a key, check if size * 100 > length * load_factor.

  If so, increase the length of the table to length * 2 + 1, and then move all the nodes

  from the old table to the new table in the order from the first to the last linked list,

  and from the head to the tail node in each linked list.

 * A word's hash code depends on its type.
   * Number: The hash code is the value of the number modulo the length of the table.

   * String: Convert the string into a multi-byte unsigned integer, where the first

     character is the most significant byte and the last character is the least significant

     byte (assuming that each character occupies only one byte). The hash code of the string

     is the value of this unsigned integer modulo the length of the table.

You may NOT use STL classes except the string class.

## Input

1.The first line of input consists of two integers, which represent load factor

  and initial length of the table, respectively.

2.The word file consists of words separated by one or more spaces (' ', '\n', '\t', or '\r').

3.The word file ends by a line of "\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*" (24 "\*"). A word may be one of two types.

    Number: A number represents an unsigned 32-bit integer in the decimal format.
    String: Any word that is not a valid number as defined above is a string.
    A string may contain any character except spaces.

4.The format of the stop word file is identical to that of the word file. Exclude stop words

  from the hash table. The stop file ends by a line of "\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*" (24 "\*").

5.Read the word file and insert its words into the hash table before reading the stop word file

  and deleting its words from the hash table.

## Output

Print the content of the hash table in the JSON format to the standard output.

    On the first line, print [

    From the first to the last element in the table, print one linked list per line.

    On each line, print:

      {
      All the nodes in the linked list from the head to the tail, separated by commas.
      For each node, print "key":value where key is a word, and value is its frequency.
      E.g., "123":1, "abc":2.
      }

    On the last line, print ]

Your program must have the same input/output behavior as my reference program.
