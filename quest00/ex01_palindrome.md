 # PSUEDOCODE 
 ``` python 
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

# CODE IMPLEMENT IN PYTHON WITH COMMENT
def is_palindrome(txt):
    # Store the original text (no cleaning done currently)
    cleaned_txt = txt
    # Create a reversed version of the text using slicing [::-1]
    reverse = cleaned_txt[::-1]
    # Return True if reversed text matches original, False otherwise
    return reverse == cleaned_txt

# Test cases
print(is_palindrome("racecar"))  # Should print: True (reads same forwards and backwards)
print(is_palindrome("hello"))     # Should print: False (hello reversed is olleh)
print(is_palindrome("A man a plan a canal Panama"))  # Currently prints: False (due to spaces and case sensitivity)
```

# What I Learned From Solving It Before Asking AI:

Breaking down String slicing in Python ([::-1]) is an elegant way to reverse strings


# How My Understanding is Different Now:

Before: I Saw palindrome as "string == reverse(string)"
I can now see it as A filtering problem where irrelevant data (non-alphanumeric) can also be ignored

# Could I Write Similar Functions Without Help Now?

Absolutely yes. The pattern recognition is now readable for easy deburging and access