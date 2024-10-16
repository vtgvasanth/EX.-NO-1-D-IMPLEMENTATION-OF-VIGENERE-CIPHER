# EX.-NO-1-D-IMPLEMENTATION-OF-VIGENERE-CIPHER

## AIM:
  To implement the Vigenere Cipher substitution technique using C program.
  
## ALGORITHM:
  STEP-1: Arrange the alphabets in row and column of a 26*26 matrix.
  
  STEP-2: Circulate the alphabets in each row to position left such that the first letter is attached to last.
 
  STEP-3: Repeat this process for all 26 rows and construct the final key matrix.
  
  STEP-4: The keyword and the plain text is read from the user.
  
  STEP-5: The characters in the keyword are repeated sequentially so as to match with that of the plain text.
  
  STEP-6: Pick the first letter of the plain text and that of the keyword as the row  indices and column indices respectively.
  
  STEP-7: The junction character where these two meet forms the cipher character.
  
  STEP-8: Repeat the above steps to generate the entire cipher text.
  
## PROGRAM:
```
def generateKey(string, key):
	key = list(key)
	if len(string) == len(key):
		return(key)
	else:
		for i in range(len(string) -
					len(key)):
			key.append(key[i % len(key)])
	return("" . join(key))
	
def cipherText(string, key):
	cipher_text = []
	for i in range(len(string)):
		x = (ord(string[i]) +
			ord(key[i])) % 26
		x += ord('A')
		cipher_text.append(chr(x))
	return("" . join(cipher_text))
	
def originalText(cipher_text, key):
	orig_text = []
	for i in range(len(cipher_text)):
		x = (ord(cipher_text[i]) -
			ord(key[i]) + 26) % 26
		x += ord('A')
		orig_text.append(chr(x))
	return("" . join(orig_text))
	
if __name__ == "__main__":
	string = "VIGNERECIPHER"
	keyword = "HELLO"
	key = generateKey(string, keyword)
	cipher_text = cipherText(string,key)
	print("Ciphertext :", cipher_text)
	print("Original/Decrypted Text :", 
		originalText(cipher_text, key))
```

## OUTPUT:
![image](https://github.com/AnnBlessy/EX.-NO-1-D-IMPLEMENTATION-OF-VIGENERE-CIPHER/assets/119477835/7d87ef69-3d96-498f-a54a-b4a8706216ac)

## RESULT:
  Thus the Vigenere Cipher substitution technique had been implemented successfully.
