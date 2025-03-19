# Zero Knowledge Proof (ZKP) Lab Report

## 1. Captured Data from Successful Run

### Step 3 - Client Signature
- **Captured Data:**

`eyJwYXJhbXMiOnsiYWxnIjoic2hhM18yNTYiLCJjdXJ2ZSI6InNlY3AyNTZrMSIsInMiOjgyODE1MDMwMzgwNjM3NDMxMTMwNDYwNzIxMzc1MzQ0Mzc2Nzk5NTEwNjMzNTgwMDI0NjM0NjA1MzQxNTc4Nzc5MDY1NjUyNDc0NDU5fSwic2lnbmF0dXJlIjo1NDgzODQ2MTA5NTM4MjgxNTM0NTYyNzkwMzMyNDY1OTE1Nzk3MzY3MDM1MzMzODYyNDE4NjExNDIwMjM2MTMxMzU2NDg5ODI1MTA4MzE4ODE1OTU4MTQ2MjY4NDQ3NDc1NjY5NTUzNzkzNDQ2NTM5OTc5NTI3NzkzNzU2OTQ4NTQ4NDE0Njg2MTQ5ODA4OTMzMjkzMzk5Mjg0NX0=`

- **Variable Name:** `signature_dump`
- **Input Data:** User-entered password (first prompt)
- **ZKP Step:** **Step 3 - Client creates a signature from their password and sends it to the server**
- **Plain Language Description:**  
The client (user) needs to prove that they know the correct password without revealing it. Instead of sending the actual password, the client generates a **digital signature** using cryptographic techniques. This signature is created using a mathematical algorithm that transforms the password into a unique encoded value. This ensures that even if someone intercepted the signature, they would not be able to determine the original password. The signature is then sent to the server, which will use it later to verify that the user knows the password.

---

### Step 6 - Server Token
- **Captured Data:**  

`45065945946037922750013951751832580368080713331800355951391596301673921557318:eyJwYXJhbXMiOnsiYWxnIjoic2hhM181MTIiLCJjdXJ2ZSI6InNlY3AzODRyMSIsInMiOjE1NjUzMjM2NzI3NDg1NTIwMTA2MzU4NTgzMzc1NzM0NjY1OTQ0NjIwODEyNjUwNjI0OTc1NTMzNjUzMTE0NTI4MjUyOTIyNjUzOTA0ODE0NDEyNTU5MzkyNTcwNTE5MjQxNDg4Mjk1OTU4MjE5ODE1OTE5fSwiYyI6MzQ3ODI4Mzk3NDAwMjUxMTc4Njc5NTY3NzE3NjE3Njg5MTM5MTQ3NTAzNTkxMTAwMDUyNTczMTUxMzgwNDc2OTA4NjU2MzA5ODU0NzE1Mjc5MjkyNjQyMzQxNDY1MzM2ODE5MjIzNTgxNDA5Nzk3MTM4NTksIm0iOjkwODE2MTAyODUyNzI4MDI5NjY4MDk1ODUwNTkwMzE1NTU5ODkwMDQ2NDkxNTg1MDM2ODkwMDEzMjIzMDcyNTI4MjQ3MDM4MzQ1MDYzMDgyMTExNTU0ODA4NzMzODg5OTQzMDU3OTk2MTIxMzk0MjYxMDQ3NzM1MjA4MzI5MDY5MzI5MjgyOTQ2MTc1MDg4OTU2MzA1OTE0MDA2MzEyNTEwMDY2MjY5Njk4MDg1Mjk4MDI1OTIzNDY4OTUzOTA5MjIwNDQyNzE5NDIwODE0NzQ5OTg1ODgwMTQzMDM4ODQ4MjYyMTA2NX0=`

- **Variable Name:** `token`
- **Input Data:** The client’s signature from Step 3
- **ZKP Step:** **Step 6 - Server sends a signed token back to the client**
- **Plain Language Description:**  
After receiving the client’s signature, the server needs to challenge the client to confirm that they actually possess the correct password. To do this, the server creates a **unique challenge token**, which is essentially a random value that the client must sign in the next step. The server digitally signs this token itself, ensuring that the token cannot be modified or faked. This step helps prevent replay attacks, where an attacker might try to reuse a previously intercepted signature.

---

### Step 8 - Client Proof
- **Captured Data:**  

`45065945946037922750013951751832580368080713331800355951391596301673921557318:eyJwYXJhbXMiOnsiYWxnIjoic2hhM181MTIiLCJjdXJ2ZSI6InNlY3AzODRyMSIsInMiOjE1NjUzMjM2NzI3NDg1NTIwMTA2MzU4NTgzMzc1NzM0NjY1OTQ0NjIwODEyNjUwNjI0OTc1NTMzNjUzMTE0NTI4MjUyOTIyNjUzOTA0ODE0NDEyNTU5MzkyNTcwNTE5MjQxNDg4Mjk1OTU4MjE5ODE1OTE5fSwiYyI6MzQ3ODI4Mzk3NDAwMjUxMTc4Njc5NTY3NzE3NjE3Njg5MTM5MTQ3NTAzNTkxMTAwMDUyNTczMTUxMzgwNDc2OTA4NjU2MzA5ODU0NzE1Mjc5MjkyNjQyMzQxNDY1MzM2ODE5MjIzNTgxNDA5Nzk3MTM4NTksIm0iOjkwODE2MTAyODUyNzI4MDI5NjY4MDk1ODUwNTkwMzE1NTU5ODkwMDQ2NDkxNTg1MDM2ODkwMDEzMjIzMDcyNTI4MjQ3MDM4MzQ1MDYzMDgyMTExNTU0ODA4NzMzODg5OTQzMDU3OTk2MTIxMzk0MjYxMDQ3NzM1MjA4MzI5MDY5MzI5MjgyOTQ2MTc1MDg4OTU2MzA1OTE0MDA2MzEyNTEwMDY2MjY5Njk4MDg1Mjk4MDI1OTIzNDY4OTUzOTA5MjIwNDQyNzE5NDIwODE0NzQ5OTg1ODgwMTQzMDM4ODQ4MjYyMTA2NX0=
eyJwYXJhbXMiOnsiYWxnIjoic2hhM18yNTYiLCJjdXJ2ZSI6InNlY3AyNTZrMSIsInMiOjgyODE1MDMwMzgwNjM3NDMxMTMwNDYwNzIxMzc1MzQ0Mzc2Nzk5NTEwNjMzNTgwMDI0NjM0NjA1MzQxNTc4Nzc5MDY1NjUyNDc0NDU5fSwiYyI6OTEyODE3MDgyMjg3MTUyNzI2MjIzOTMyNTAxMjk5MTAxNTEyMzA3Nzk1ODMxNjU2ODQzMjk5NjIyMjA5MzE2NjQwOTMxNDkzODcxODMsIm0iOjU1NzgwMjE1Njg0MjgzNzc0MzM5NTUyODYwNjUxMTg4ODI2Mzc4MTEzMDI4MDUxMTkzNjMwOTc0NTcwNDE1NTE5MTEwNTkxODUwNzQ2MDc2ODM5MTMxMzk4ODM5OTA1ODk3MzcxOTA1OTEyMDIwNDQxNDU2NjI2NjMwODkxOTY3ODIwMzc3MzQ5MDY2MDcxOTEzNjI3MDUwNDF9`

- **Variable Name:** `proof`
- **Input Data:** User-entered password (second prompt) + received token from Step 6
- **ZKP Step:** **Step 8 - Client generates a proof using the password and token**
- **Plain Language Description:**  
To prove that they truly know the password, the client must now sign the token received from the server. This signing process depends on the second password input. If the client enters the same password as before, the signature will be valid and will match the expected proof. However, if the password is different, the signature will not match. This step is crucial because it ensures that the client is proving knowledge of the password **without revealing what the password actually is**. The client then sends this proof back to the server.

---

### Step 10 - Authentication Result
- **Captured Data:**  

`Success!`

- **Variable Name:** `result`
- **Input Data:** The server's verification of the proof
- **ZKP Step:** **Step 10 - Server verifies proof and sends authentication result**
- **Plain Language Description:**  
The server now checks the proof sent by the client. If the proof is valid, it confirms that the client knows the correct password and the authentication is successful. The server then sends back a **Success!** message. Since the client never actually sent the password, the server does not store or learn the actual password—only whether the proof is correct. This maintains the security and confidentiality of the authentication process.

---

## 2. Captured Data from Unsuccessful Run

### Step 3 - Client Signature
- **Captured Data:**  

`eyJwYXJhbXMiOnsiYWxnIjoic2hhM18yNTYiLCJjdXJ2ZSI6InNlY3AyNTZrMSIsInMiOjY0Mjk1NTA0NzY4MTYxNTYwNTM0NDY0NTk2MTI1Mjk5MjMzNDQ0NTIxNjQ3Njk5MjM1MjI4NjM5NjE2MzIwMzkzNDM5NTQ1NzI3NDI2fSwic2lnbmF0dXJlIjo2NjY2OTM5Njc1NzE0Mzc2MDMwODU4Mzk3NTgzNDI0Nzg5MTIwNzk3MjEyNjA2NzQ4NjY3MTc0MDU3MzQ1Mzk2MjExMzQ3MjI4NTQ0OTE0Mzg1Mjg0NTM2MjY2NDA3MTMwNTc3OTg4NDU0NTIyNTcwOTEzNzcyMDA4NDk3NjAyNzIwNTMxMDcxMzM5ODg5MzQyMDExMTAyNjkxMH0=`

- **Variable Name:** `signature_dump`
- **Input Data:** User-entered password (first prompt)
- **ZKP Step:** **Step 3 - Client creates a signature from their password and sends it to the server**
- **Plain Language Description:**  
This step is identical to the successful run. The client generates a cryptographic signature based on the first password entered and sends it to the server.

---

### Step 6 - Server Token
- **Captured Data:**  

`2035840852164320561545851407858961300476372007535475614062679982356772089888:eyJwYXJhbXMiOnsiYWxnIjoic2hhM181MTIiLCJjdXJ2ZSI6InNlY3AzODRyMSIsInMiOjE5NjA0NzE2MzcwMDM4Mzc2NDYxNjgyMjMwMTE2MzI3NDU5NzEyNDU1ODA0NTcyODY2ODM0NTU2NzgzNzI5MzI0NTIzMzM1MzMxNzgzNzg5ODU2OTAyOTY4ODgxNjcyNjMyODMzNDcyNjI3MzM3Mjg2MTIxfSwiYyI6Mjk0MjM5MTQyMDEyNzk0NjI2MjMwMTM4MzUxMjQ4MTk4ODQ1MTU5NTU3NTY2NDE0NzUyMTA4NDQxNTYzOTU5ODM4MzQ5Njg4MTMyMDAzNDEwMjk4NDg3Mzc5NDA4NjI5ODUyOTMzNjU2NjE1NTQ5NzYyODUsIm0iOjMyMDEwOTcwOTUzNjk2OTg1MjkxMjQ2MTQyNTkxMjA2NTc3MTM5NTc0NDQ0MjExNTc1OTgyMDc4NzA3MzUzNDY4OTI0MDE2MzQ5MzEwOTg5NjM0MzgxMjg0NzY3NzY1NjA3NTIwNTc2NDAwOTYwOTU3NDYyNzg0ODg4MTg1MTA0NjA3MDY4NTY4MTczODc5NDM2MjU2MzYyNTY1ODkyODg3MjU5Mzg2NTI4NDAwNjY1NDg1MDk3MzU3NDgzMTU3NjY3NDQ1ODQ4MjU3NDI5MDc0ODQ4ODEyOTQ2MTMxNzA2MjM4MjU5fQ==`

- **Variable Name:** `token`
- **Input Data:** The client’s signature from Step 3
- **ZKP Step:** **Step 6 - Server sends a signed token back to the client**
- **Plain Language Description:**  
The server generates a new challenge token, just as in the successful run, and sends it to the client. Since the client’s first password was the same, this token generation process is consistent.

---

### Step 8 - Client Proof
- **Captured Data:**  

`2035840852164320561545851407858961300476372007535475614062679982356772089888:eyJwYXJhbXMiOnsiYWxnIjoic2hhM181MTIiLCJjdXJ2ZSI6InNlY3AzODRyMSIsInMiOjE5NjA0NzE2MzcwMDM4Mzc2NDYxNjgyMjMwMTE2MzI3NDU5NzEyNDU1ODA0NTcyODY2ODM0NTU2NzgzNzI5MzI0NTIzMzM1MzMxNzgzNzg5ODU2OTAyOTY4ODgxNjcyNjMyODMzNDcyNjI3MzM3Mjg2MTIxfSwiYyI6Mjk0MjM5MTQyMDEyNzk0NjI2MjMwMTM4MzUxMjQ4MTk4ODQ1MTU5NTU3NTY2NDE0NzUyMTA4NDQxNTYzOTU5ODM4MzQ5Njg4MTMyMDAzNDEwMjk4NDg3Mzc5NDA4NjI5ODUyOTMzNjU2NjE1NTQ5NzYyODUsIm0iOjMyMDEwOTcwOTUzNjk2OTg1MjkxMjQ2MTQyNTkxMjA2NTc3MTM5NTc0NDQ0MjExNTc1OTgyMDc4NzA3MzUzNDY4OTI0MDE2MzQ5MzEwOTg5NjM0MzgxMjg0NzY3NzY1NjA3NTIwNTc2NDAwOTYwOTU3NDYyNzg0ODg4MTg1MTA0NjA3MDY4NTY4MTczODc5NDM2MjU2MzYyNTY1ODkyODg3MjU5Mzg2NTI4NDAwNjY1NDg1MDk3MzU3NDgzMTU3NjY3NDQ1ODQ4MjU3NDI5MDc0ODQ4ODEyOTQ2MTMxNzA2MjM4MjU5fQ==
eyJwYXJhbXMiOnsiYWxnIjoic2hhM18yNTYiLCJjdXJ2ZSI6InNlY3AyNTZrMSIsInMiOjY0Mjk1NTA0NzY4MTYxNTYwNTM0NDY0NTk2MTI1Mjk5MjMzNDQ0NTIxNjQ3Njk5MjM1MjI4NjM5NjE2MzIwMzkzNDM5NTQ1NzI3NDI2fSwiYyI6MTE1MDY5MDExNDE3ODEyNTc5MjQ3NzM3MTc2MTYwNzg5NDA3NTM3NTc4NTU0ODcxMTUzMjg0MTgzMzY1MDQ2Mjk4MTY1NjQ1NTMzNTM4LCJtIjoyMjg1NjkyODAzNzg0OTk5MjM3MjQ2OTU1MTQxMDAwMDM3NjA0ODQ5MjI2Mjg1ODIxMjIxMjk3MDg5ODk5Mjg5NDE2ODI4ODMwNTIzMzUzMDMxOTYwMTkxNjk5OTAwMjMyMjYwMDQ1NjE2OTU4MzYwNDY5NDI3MDg3MDAyNzY4MDUxMzQ2MjQyMjAwNzU4ODM4ODQzMzY5MjY2fQ==`

- **Variable Name:** `proof`
- **Input Data:** **(Incorrect)** second password + received token from Step 6
- **ZKP Step:** **Step 8 - Client generates a proof using the password and token**
- **Plain Language Description:**  
In this run, the client mistakenly enters a different second password. Because the proof is created using this password, it will **not match** the expected proof that the server is looking for. Since the proof is incorrect, the server will recognize that the client does **not** actually know the correct password.

---

### Step 10 - Authentication Result
- **Captured Data:**  

`Failure!`

- **Variable Name:** `result`
- **Input Data:** The server's verification of the proof
- **ZKP Step:** **Step 10 - Server verifies proof and sends authentication result**
- **Plain Language Description:**  
The server verifies the proof and finds that it is invalid. This happens because the proof was generated using the wrong password, so it does not match what the server expected. As a result, authentication **fails**. This demonstrates that an attacker who does not know the password cannot trick the server into granting access.

---

## 3. Evaluation of Zero Knowledge Proof Properties

### Completeness
- **Definition:** If the prover (client) is honest and provides correct input, the verifier (server) will always accept the proof.
- **Does the program meet this requirement?** ✅ **Yes**
- **Explanation:** The successful authentication proves that when the correct password is used, authentication is always granted.

---

### Soundness
- **Definition:** A cheating prover (client) cannot convince the verifier (server) without actually knowing the password.
- **Does the program meet this requirement?** ✅ **Yes**
- **Explanation:** The unsuccessful authentication attempt proves that entering the wrong password leads to authentication failure, ensuring that an attacker cannot fake knowledge of the password.

---

### Zero Knowledge
- **Definition:** The verifier (server) does not learn any useful information about the password.
- **Does the program meet this requirement?** ✅ **Yes**
- **Explanation:** The server never sees the actual password; it only sees cryptographic proofs, ensuring that no sensitive data is leaked.

---

### Conclusion
This program successfully implements a Zero Knowledge Proof (ZKP) authentication system while maintaining security, correctness, and confidentiality.



