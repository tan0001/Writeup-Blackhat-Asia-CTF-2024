Name : Crypto 101

Points : 75

Description :
Below is some weird cipher text we found from an admin's bash_history. We haven't been able to figure it out yet. Can you help?

Y1hCMGRIQjFaaUJxZVhCcWNteGhlaXdnWVc5d2VpQnFiMmh6YzJ4MWJteDZJSEI2SUdGMlltNXZJU0J0YzJodWUycG9iSHBvZVY5NmFITm9hM3BmYUhsc1gyaGZkR3g2ZW4wPT09

Solution :
So firstly I tried to decode this text as Base64, and we get the following.

![image](https://github.com/tan0001/Writeup-Blackhat-Asia-CTF-2024/assets/115548054/8f5a92ee-8fbd-473b-ac57-51783b804bb4)

Decode the output once more, and we get encrypted text.

![image](https://github.com/tan0001/Writeup-Blackhat-Asia-CTF-2024/assets/115548054/d5c5d7e8-c293-4e2b-a213-0d22c2bec3d4)

mshn = flag : This is shift cipher with shift of 7 or 26-7 = 19. We get the flag on decrypting.

![image](https://github.com/tan0001/Writeup-Blackhat-Asia-CTF-2024/assets/115548054/8489a878-f212-44ae-9055-f6c66fc6b78c)


Flag : flag{caesar_salads_are_a_mess}
