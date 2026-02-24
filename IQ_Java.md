# **Key Features of the Query Service (Read Side)**  

# 1. Anagram
```
String s1 = "listen";
String s2 = "silent";

char[] strChar = s1.toCharArray();
Arrays.sort(strChar);

char[] strChar2 = s2.toCharArray();
Arrays.sort(strChar2);

if(Arrays.equals(strChar, strChar2)){
    System.out.println("Anagram");
} else {
    System.out.println("Not Anagram");
}
```
