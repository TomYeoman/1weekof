# Question

Write an autocomplete class that returns all dictionary words with a given prefix.

E.G

```
dict:   {"abc", "acd", "bcd", "def", "a", "aba"}

prefix: "a" -> "abc", "acd", "a", "aba"
prefix: "b" -> "bcd"
```

Extension : The dictionary / map also has a weight attribute for each entry, Consider how we may solve this

## Tips

Do not rush the question, instead we should think of all the cases we should allow for, Start with naive approaches and work our way up

	1. Consider the response time ( E.G < no query should take over 100ms )
	2. Consider ranking ( We already have it defined )
	3. Uppercase VS lowercase
	4. Alphanumeric considerions
	5. User specific
	6. Certain keywords may


We can assume all characters are lowercase ( We could uppercase before operating etc ) + alphanumeric
	*
Uppercase VS lowercase
	*
Worrying about alphanumeric?

# Solution

### Brute force

```javascript
/**
 * Brute force implementation O(n)
 */

const SEARCH_TERMS = {
  "DRESSING TABLE" : "100",
  "DRESS" : 50,
  "DRESSING TABLE MIRROR" : 25
}
const PREFIX = "DRESS";
const refinedSearch = {}

Object.entries(SEARCH_TERMS).forEach(([key, value]) => {
  if (key.includes(PREFIX)) refinedSearch[key] = value;
})

console.log(refinedSearch)

```

### Trie

  * Distrubted TRIE
  * Optimising for time, or space
    * Space isn't a concern - Pre-cache results for any given prefix within a map, allowing for O(1) lookup times
    * Space is then use a standard TRIE

```java
// Trie node class
private class Node {
    String prefix;
    HashMap<Character, Node> children;

    // Does this node represent the last character in a word?
    boolean isWord;

    private Node(String prefix) {
        this.prefix = prefix;
        this.children = new HashMap<Character, Node>();
    }
}

// The trie
private Node trie;

// Construct the trie from the dictionary
public Autocomplete(String[] dict) {
    trie = new Node("");
    for (String s : dict) insertWord(s);
}

// Insert a word into the trie
private void insertWord(String s) {
    // Iterate through each character in the string. If the character is not
    // already in the trie then add it
    Node curr = trie;
    for (int i = 0; i < s.length(); i++) {
        if (!curr.children.containsKey(s.charAt(i))) {
            curr.children.put(s.charAt(i), new Node(s.substring(0, i + 1)));
        }
        curr = curr.children.get(s.charAt(i));
        if (i == s.length() - 1) curr.isWord = true;
    }
}

// Find all words in trie that start with prefix
public List<String> getWordsForPrefix(String pre) {
    List<String> results = new LinkedList<String>();

    // Iterate to the end of the prefix
    Node curr = trie;
    for (char c : pre.toCharArray()) {
        if (curr.children.containsKey(c)) {
            curr = curr.children.get(c);
        } else {
            return results;
        }
    }

    // At the end of the prefix, find all child words
    findAllChildWords(curr, results);
    return results;
}

// Recursively find every child word
private void findAllChildWords(Node n, List<String> results) {
    if (n.isWord) results.add(n.prefix);
    for (Character c : n.children.keySet()) {
        findAllChildWords(n.children.get(c), results);
    }
}

```
