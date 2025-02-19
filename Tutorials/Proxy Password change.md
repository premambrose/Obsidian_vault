# Step 1: Create a plaintext password file
`echo "my_secure_password" > password.txt`
or
`vi/nano password.txt`

# Step 2: Encrypt the plaintext password file
`openssl aes-256-cbc -salt -in password.txt -out v -iter 20`

# Step 3: Remove the plaintext password file
`rm password.txt`
