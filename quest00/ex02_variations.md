# Modified palindrome function that meet Ignore spaces and punctuation,Be case-insensitive, Return the position where the string stops being a palindrome (if not one).
def is_palindrome(txt):
    cleaned_txt = txt.replace(" ", "").lower()
    reverse = cleaned_txt[::-1]  # Fixed: using the correct variable name
    return reverse == cleaned_txt

print(is_palindrome("racecar"))  # Output: True
print(is_palindrome("hello"))
print(is_palindrome("A man a plan a canal panama"))



    
# After your first attempt, ask AI:
    whitespace strings: my function would work but better to handle explicitly

    Non-English letters: .isalnum() works but normalization helps with special characters

    Efficiency: Two-pointer approach is more memory-efficient than slicing

# 3 Reflect on what AI added that i didn't consider initially
 This shows how easy it is to get locked into a particular solution pattern. The AI helped break that pattern by asking "What if we don't build the cleaned string at all?" - a question I should have asked myself during optimization.
