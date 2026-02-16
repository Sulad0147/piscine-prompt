def is_palindrome(txt):

    cleaned_txt = txt.replace(" ", "").lower()
    
    reverse = cleaned_txt[::-1]
    
    return reverse == cleaned_txt


# Test cases
print(is_palindrome("racecar"))  # True
print(is_palindrome("hello"))     # False
print(is_palindrome("A man a plan a canal panama"))  # True
    
    
    RETURN TRUE
 

 # PSUEDOCODE PYTHON IMPLEMENTATION WITH COMMENT
 def is_palindrome(txt):
    # Clean the text: remove spaces and convert to lowercase
    # This handles phrases with spaces and mixed case
    cleaned_txt = txt.replace(" ", "").lower()
    
    # Getting the reverse of cleaned text
    reverse = cleaned_txt[::-1]
    
    # Check if the reversed text is equal to the cleaned text
    return reverse == cleaned_txt


# Test cases
print(is_palindrome("racecar"))  # True
print(is_palindrome("hello"))     # False
print(is_palindrome("A man a plan a canal panama"))  # True


# Test cases
test_cases = ["racecar", "hello", "A man a plan a canal Panama"]
for test in test_cases:
    print(f"'{test}': {is_palindrome(test)}")

# What I Learned From Solving It Before Asking AI:

Breaking down "palindrome with non-alphanumeric filtering" into: Pointer movement, Character validation, Case normalization and Comparison logic


# How My Understanding is Different Now:

Before: I Saw palindrome as "string == reverse(string)"
I can now see it as A filtering problem where irrelevant data (non-alphanumeric) can also be ignored

# Could I Write Similar Functions Without Help Now?

Absolutely yes. The pattern recognition is now readable for easy deburging 