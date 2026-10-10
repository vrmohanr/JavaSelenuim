# Java Syntax Cheat Sheet (SDET Interview)

## Conversions
```java
int n = Integer.parseInt("123");            // String → int
String s = String.valueOf(123);             // int → String
String s = "" + 123;                        // int → String (shortcut)
String s = String.valueOf('a');             // char → String
char c = "abc".charAt(0);                   // String → char
int d = '7' - '0';                          // digit char → int (7)
char c = (char) (n + '0');                  // int digit → char
int ascii = (int) 'A';                      // char → ASCII (65)
char c = (char) 97;                         // ASCII → char ('a')
char[] arr = text.toCharArray();            // String → char[]
String s = new String(arr);                 // char[] → String
String[] words = text.split(" ");           // String → words
String[] words = text.trim().split("\\s+"); // split on any spaces
String s = String.join(" ", words);         // words → "ram sit sobha"
```

## String methods
```java
s.length()                                  // length (with brackets)
s.charAt(i)                                 // char at index i
s.substring(2)                              // from index 2 to end
s.substring(1, 4)                           // index 1 to 3 (end excluded)
s.indexOf('a')                              // position, or -1 if not found
s.contains("abc")                           // true/false (String only)
s.equals("abc")                             // compare Strings (never ==)
s.equalsIgnoreCase("ABC")                   // compare ignoring case
s.toUpperCase()  /  s.toLowerCase()         // change case
s.trim()                                    // remove start/end spaces
s.replace("a", "b")                         // replace all
s.isEmpty()                                 // true if ""
s.startsWith("ab")  /  s.endsWith("yz")     // check start/end
w.substring(0, 1).toUpperCase() + w.substring(1)  // capitalize word
new StringBuilder(s).reverse().toString()   // reverse a String
```

## Character checks
```java
Character.isLetter(ch)                      // a–z, A–Z
Character.isDigit(ch)                       // 0–9
Character.isLetterOrDigit(ch)               // letter or digit
Character.isWhitespace(ch)                  // space
Character.isUpperCase(ch)  /  isLowerCase   // case check
Character.toUpperCase(ch)  /  toLowerCase   // change case
"aeiou".indexOf(ch) != -1                   // is vowel
```

## StringBuilder
```java
StringBuilder sb = new StringBuilder();     // create
sb.append("x");                             // add to end
sb.insert(0, "x");                          // add at start
sb.deleteCharAt(sb.length() - 1);           // remove last char
sb.toString()                               // back to String
```

## Arrays
```java
int[] a = {4, 2, 7};                        // create with values
int[] a = new int[5];                       // empty, size 5 (all 0)
a.length                                    // size (no brackets)
a[0]                                        // first element
a[a.length - 1]                             // last element
for (int i = 0; i < a.length; i++)          // loop with index
for (int x : a)                             // loop values
Arrays.sort(a);                             // sort ascending
Arrays.toString(a)                          // print "[2, 4, 7]"
Arrays.equals(a, b)                         // compare two arrays
int max = Integer.MIN_VALUE;                // start for finding max
int min = Integer.MAX_VALUE;                // start for finding min
```

## ArrayList
```java
List<Integer> list = new ArrayList<>();     // create
list.add(5);                                // add
list.get(0)                                 // get by index
list.size()                                 // size
list.contains(5)                            // check exists
list.remove(Integer.valueOf(5));            // remove value
Collections.sort(list);                     // sort
Collections.reverse(list);                  // reverse
```

## HashMap
```java
Map<Character, Integer> map = new HashMap<>();   // create
map.put(k, v);                                   // add/update
map.get(k)                                       // value (null if missing)
map.getOrDefault(k, 0)                           // value or 0
map.put(k, map.getOrDefault(k, 0) + 1);          // COUNT pattern
map.containsKey(k)                               // key exists?
map.remove(k);                                   // delete
map.size()                                       // number of keys
for (char k : map.keySet())                      // loop keys
for (int v : map.values())                       // loop values
for (Map.Entry<Character, Integer> e : map.entrySet())  // loop pairs
e.getKey()  /  e.getValue()                      // inside entry loop
new LinkedHashMap<>()                            // keeps insert order
new TreeMap<>()                                  // sorted keys
map.computeIfAbsent(k, x -> new ArrayList<>()).add(v);  // GROUP pattern
```

## HashSet
```java
Set<Integer> set = new HashSet<>();         // create (no duplicates)
set.add(x)                                  // returns false if already there
set.contains(x)                             // check exists
```

## Imports
```java
import java.util.*;                         // covers all of the above
```

## Common patterns
```java
for (int i = s.length() - 1; i >= 0; i--)   // loop backward
if (n % 2 == 0)                             // even
n % 10                                      // last digit
n / 10                                      // remove last digit
for (int i = 1; i < a.length; i++)  a[i] vs a[i-1]   // compare neighbours
int temp = a[i]; a[i] = a[j]; a[j] = temp;  // swap
```
