# **Java Basic Code Interview**  

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
# 2. Count the Sequence of Character
```
String str = "Java";
Map<Character, Integer> mp  = new HashMap<>();

char[] char1 = str.toCharArray();
for(char c: char1){
    mp.put(c, mp.getOrDefault(c, 0) + 1);
}

mp.entrySet().stream().forEach((k) -> System.out.println(k.getKey() + " <> " +k.getValue()));
```
# 3. Find a Palindrome Integer
```
Integer val = 121;
int original = val;
int reverse = 0;

while(val > 0){ //iterating 3 times
    reverse = reverse * 10 + (val % 10); // reverse multiply by 10 + input module(%) by 10
    val /= 10; // input divided by 10
}

if(original == reverse){
    System.out.println("This number are Palindrome");
} else {
    System.out.println("This number are not Palindrome");
}
```
# 4. Reverse Integer
```
Integer val = 143;
int reverse = 0;

while(val > 0){ //iterating 3 times
    reverse = reverse * 10 + (val % 10); // reverse multiply by 10 + input module(%) by 10
    val /= 10; // input divided by 10
}
System.out.println("reverse :: " + reverse);
```




