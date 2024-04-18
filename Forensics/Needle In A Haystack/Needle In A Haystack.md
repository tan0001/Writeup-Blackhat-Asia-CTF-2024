Name : Needle In A Haystack

Points : 125

Description :

Shift thrice, then unveil the disguise

Julius Caesar Never

Solution :

We are provided with a JSON file, with data fields as timestamp, ip, request, and status. We are interested in the request field which contains some data.
1st block is a base64 encoding which decodes to a POST request.

![image](https://github.com/tan0001/Writeup-Blackhat-Asia-CTF-2024/assets/115548054/abcdc55a-f226-400c-b7e6-7ce929f6a54d)

2nd block contains some characters but it is neither base64, nor hexadecimal, so we'll skip that for now.
3rd block contains hexadecimal data, which is converted to base64 first. This base64 is the same data as in block 1.

![image](https://github.com/tan0001/Writeup-Blackhat-Asia-CTF-2024/assets/115548054/e3cc73c1-0576-4600-bbb8-7e224990f9fb)

Block 4,5 have some random characters so skipping it for now.
Block 6 and 7 have the same Base64 data, which is a GET request.

![image](https://github.com/tan0001/Writeup-Blackhat-Asia-CTF-2024/assets/115548054/38245204-10c0-4333-8092-add825f340d3)

8th block contains hexadecimal data, so let's convert it to Base64. This is the same data as in block 6 and 7.

![image](https://github.com/tan0001/Writeup-Blackhat-Asia-CTF-2024/assets/115548054/3fbec26d-fead-4bee-aac3-abbd8b5cf355)

Skipping the data in 9th and 10th block, 11th block gives us the goldmine. The data is in hex so convert it to Base64.

![image](https://github.com/tan0001/Writeup-Blackhat-Asia-CTF-2024/assets/115548054/4a4e6983-0a18-44ad-be40-0025a400806f)

Decoding this base64 gives another base64 encoding, which leads us to believe that this might be the flag.

![image](https://github.com/tan0001/Writeup-Blackhat-Asia-CTF-2024/assets/115548054/54ff0624-a706-45c7-b574-85b46b686af8)
![image](https://github.com/tan0001/Writeup-Blackhat-Asia-CTF-2024/assets/115548054/62facf6c-169c-4766-9875-8c51a8c3b864)

This is simple Caesar shift cipher, with a shift of 3 or 26-3 = 23. Decrypting this gives us the flag.

![image](https://github.com/tan0001/Writeup-Blackhat-Asia-CTF-2024/assets/115548054/5bb7be6f-8b7d-4a92-a36c-bf4f5897b49d)


Flag : flag{parse_the_parcel}
