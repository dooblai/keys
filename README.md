## Generate private key

openssl genrsa -out key.pem 4096

## Generate public key from private key

openssl rsa -in key.pem -pubout -out pub.pem


## How to encrypt a file

If you put the secrets in a file called secret.txt you may use following command to encrypt it:
openssl rsautl -encrypt -inkey pub.pem -pubin -in secret.txt -out encrypted.bin

and then share the encrypted.bin file.

## How to decrypt an encrypted file

openssl rsautl -decrypt -inkey key.pem -in encrypted.bin
