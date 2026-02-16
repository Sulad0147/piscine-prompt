# Modified palindrome function that meet Ignore spaces and punctuation,Be case-insensitive, Return the position where the string stops being a palindrome (if not one).
def is_palindrome(txt):
    # Remove spaces and punctuation, convert to lowercase
    cleaned = []
    original_indices = []  # Store original indices of kept characters
    
    for i, char in enumerate(txt):
        if char.isalnum():  # Keep only alphanumeric characters
            cleaned.append(char.lower())
            original_indices.append(i)
    
    # Convert to string for easier comparison
    cleaned_txt = ''.join(cleaned)
    
    # Check if it's a palindrome and find mismatch position
    for i in range(len(cleaned_txt) // 2):
        if cleaned_txt[i] != cleaned_txt[-(i + 1)]:
            # Return the original position of the first mismatched character
            return original_indices[i]
    
    return True  # It's a palindrome
# After your first attempt, ask AI:
    Empty/whitespace strings: Your function would work but better to handle explicitly

    Accented characters: Added Unicode normalization for characters like "café" → "cafe"

    Non-English letters: .isalnum() works but normalization helps with special characters

    Efficiency: Two-pointer approach is more memory-efficient than slicing

# 3 Reflect on what AI added that i didn't consider initially
 This shows how easy it is to get locked into a particular solution pattern. The AI helped break that pattern by asking "What if we don't build the cleaned string at all?" - a question I should have asked myself during optimization.
