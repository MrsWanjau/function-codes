#QUESTION ONE
#Design a function that reverses the digits of an integer. For exampe, 50 should become 5 and -12 should become -21 
def reverse_integer(x):
    # Convert integer to string
    s = str(x)
    
    # Handle negative sign if present
    if s[0] == '-':
        reversed_s = '-' + s[:0:-1]  # Reverse string excluding '-'
    else:
        reversed_s = s[::-1]  # Reverse entire string
    
    # Convert reversed string back to integer
    reversed_int = int(reversed_s)
    
    return reversed_int


print(reverse_integer(12345))

#QUESTION TWO
#Write a recursive function to calculate factorial of a number
def factorial(n):
    # Base case: factorial of 0 is 1
    if n == 0:
        return 1
    # Recursive case: factorial of n is n times factorial of (n-1)
    else:
        return n * factorial(n - 1)

print(factorial(10))

#QUESTION THREE
#Design a function that takes a string or sequence of characters as input and returns the character that appears most frequently            
//Eg 11189=>'1'                
//hello =>l
def most_frequent_char(input_string):
    if not input_string:
        return None
    
    # Dictionary to store character counts
    char_count = {}
    
    # Count frequencies of each character
    for char in input_string:
        if char in char_count:
            char_count[char] += 1
        else:
            char_count[char] = 1
    
    # Initialize variables to track max frequency and corresponding character
    max_count = 0
    frequent_char = ''
    
    # Find the character with the maximum frequency
    for char, count in char_count.items():
        if count > max_count:
            max_count = count
            frequent_char = char
    
    return frequent_char

print(most_frequent_char('11189'))  

#QUESTION FOUR
#Design a function that determines whether a given string is a pangram. A pangram is a sentence or phrase containing every letter of the alphabet at at least once . Punctuation and case are typically ignore. For example the string "The quick brown fox jumps over the lazy dog" is a pangram, while "Hello, world!" is not
import string

def is_pangram(input_string):
    # Create a set of all lowercase letters
    alphabet_set = set(string.ascii_lowercase)
    
    # Convert input_string to lowercase and remove non-alphabetic characters
    clean_string = ''.join(char.lower() for char in input_string if char.isalpha())
    
    # Convert clean_string to a set of characters
    input_set = set(clean_string)
    
    # Check if all letters in alphabet_set are in input_set
    return alphabet_set <= input_set


print(is_pangram("The quick brown fox jumps over the lazy dog")) 
print(is_pangram("Hello, world!"))  

#QUESTION FIVE
#Design a function that takes a list of integers as input.The function should return true if the list contains two consecutive threes(3 next to 3)anywhere within the list.Otherwise, it should return false.For example, the function should return true for [1,3,3] AND FALSE FOR [1,3,1,3]
def has_two_consecutive_threes(nums):
    # Iterate through the list up to the second last element
    for i in range(len(nums) - 1):
        # Check if the current element and the next element are both 3
        if nums[i] == 3 and nums[i + 1] == 3:
            return True
    # If no consecutive threes were found, return False
    return False

print(has_two_consecutive_threes([1, 3, 3]))     # Output:
print(has_two_consecutive_threes([1, 3, 1, 3]))  # Output:

#QUESTION SIX
#Master Yoda a renowed Jedi Master from the Star Wars universe, is known for his unique way of speaking.He often reverses the order of words in his sentences. For example instead of saying "i am home" he might say "home am i" Design a function that takes a sentence as input and and returns a new sentense with the words reversed in the same order that Master Yoda would use
def reverse_sentence(sentence):
    # Split the sentence into words
    words = sentence.split()
    
    # Reverse the list of words
    reversed_words = words[::-1]
    
    # Join the reversed list of words into a new sentence
    reversed_sentence = ' '.join(reversed_words)
    
    return reversed_sentence


input_sentence = "May the Force be with you"
output_sentence = reverse_sentence(input_sentence)
print(output_sentence)  




