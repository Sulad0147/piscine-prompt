# PSUEDOCODE 
FUNCTION is_palindrome_optimized(s):
    left = 0
    right = length(s) - 1
    
    WHILE left < right:
        
        WHILE left < right AND NOT is_alphanumeric(s[left]):
            left = left + 1
        END WHILE
        
        
        WHILE left < right AND NOT is_alphanumeric(s[right]):
            right = right - 1
        END WHILE
        
        
        IF lowercase(s[left]) != lowercase(s[right]):
            RETURN FALSE
        END IF
        
        left = left + 1
        right = right - 1
    END WHILE
    
    RETURN TRUE
END FUNCTION
 

 # PSUEDOCODE PYTHON IMPLEMENTATION WITH COMMENT
 def is_palindrome(s):
    """
    Checks if a string is a palindrome, ignoring case and non-alphanumeric characters.
    """
    # Step 1: Clean the string – keep only alphanumeric characters, convert to lowercase
    clean = ""
    for char in s:
        if char.isalnum():               # Check if character is letter or number
            clean += char.lower()        # Add lowercase version to clean string
    
    # Step 2: Two-pointer approach to compare characters from both ends
    left = 0
    right = len(clean) - 1
    
    while left < right:
        if clean[left] != clean[right]:  # If mismatch found, it's not a palindrome
            return False
        left += 1                        # Move pointers inward
        right -= 1
    
    # Step 3: All characters matched
    return True

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