# Modified palindrome function that meet Ignore spaces and punctuation,Be case-insensitive, Return the position where the string stops being a palindrome (if not one).
def is_palindrome(s):
    """
    Checks if a string is a palindrome, ignoring case, spaces, and punctuation.
    Returns a tuple: (is_palindrome, position)
    - is_palindrome: True/False
    - position: -1 if palindrome, otherwise index where mismatch occurs in cleaned string
    """
    # Step 1: Clean the string – keep only alphanumeric characters, convert to lowercase
    clean = ""
    for char in s:
        if char.isalnum():               # Check if character is letter or number
            clean += char.lower()        # Add lowercase version to clean string
    
    # Handle empty or single character cleaned strings
    if len(clean) <= 1:
        return (True, -1)  # Empty or single character strings are palindromes
    
    # Step 2: Two-pointer approach to compare characters from both ends
    left = 0
    right = len(clean) - 1
    
    while left < right:
        if clean[left] != clean[right]:  # If mismatch found
            # Return False and the position where it fails
            # Position is based on the cleaned string
            return (False, left)
        left += 1
        right -= 1
    
    # Step 3: All characters matched - it's a palindrome
    return (True, -1)

# Alternative version that returns original string position
def is_palindrome_with_original_position(s):
    """
    Returns position in ORIGINAL string where palindrome fails.
    Returns a tuple: (is_palindrome, position_in_original_string)
    """
    # Build clean string and track original positions
    clean = ""
    original_positions = []  # Maps clean index -> original index
    
    for i, char in enumerate(s):
        if char.isalnum():
            clean += char.lower()
            original_positions.append(i)
    
    if len(clean) <= 1:
        return (True, -1)
    
    left = 0
    right = len(clean) - 1
    
    while left < right:
        if clean[left] != clean[right]:
            # Convert clean position back to original position
            return (False, original_positions[left])
        left += 1
        right -= 1
    
    return (True, -1)

# 3 Reflect on what AI added that i didn't consider initially
 This shows how easy it is to get locked into a particular solution pattern. The AI helped break that pattern by asking "What if we don't build the cleaned string at all?" - a question I should have asked myself during optimization.
