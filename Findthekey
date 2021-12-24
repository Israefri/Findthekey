from Crypto.Cipher import AES

# This program responsible to find a valid AES (128bit) key for decryption of cipher text to clear-text

BLOCK_SIZE = 16 # represent 128bit AES key

def readKey():
    with open("keysomewhere.dat", "rb") as file:
        f = file.read()
    return f

def readEncryptedText():
    with open("msg.dat", "rb") as file:
        f = file.read()
    return f

def decryptText(key, msg):
    for i in range(0, len(key) - BLOCK_SIZE):
        tempKey = key[i: i + BLOCK_SIZE]
        cipher = AES.new(tempKey, AES.MODE_ECB)

        try:
            plainText = cipher.decrypt(msg)
            if plainText.isascii():
                print("The decrypted message is:")
                print(plainText.decode("utf-8"))
                print("\nUsing the valid key: {}".format(tempKey))
        except Exception as e:
            print(e)

def main():
    key = readKey()
    msg = readEncryptedText()

    # Start decrypting the cipher text
    decryptText(key, msg)

if __name__ == "__main__":
    main()
