##PixSafe

PixSafe is a simple file-to-image encoding tool that converts any file into a PNG image by mapping its binary data to pixel values. It provides a basic layer of security by applying an XOR-based encryption using a user-provided password.

Features

File-to-Image Conversion:
Converts files (any type) into an image by encoding each byte of the file as pixel data.

Basic Encryption:
Uses an XOR cipher to encrypt the file’s binary data with a password. This obfuscates the data before it is embedded into the image.

Metadata Embedding:
Stores file metadata (such as the file extension) within the encoded image to facilitate proper decoding.

Simple Web Interface:
An easy-to-use HTML interface with file input, password field, and a canvas element that renders the generated image.


How It Works

1. File Input:
The user selects a file to encode and enters a password.


2. Encryption:
The file’s binary data is read and encrypted using an XOR cipher that cycles through the bytes of the provided password.


3. Metadata Storage:
The file extension (and potentially other metadata) is stored as JSON. A separator byte is used to distinguish metadata from the encrypted file data.


4. Image Generation:
The combined metadata and encrypted data are mapped to pixel values on an HTML canvas. Each byte of data is set as the R, G, and B values (with the alpha channel set to 255), forming a square image.


5. Download:
The canvas is converted into a PNG image, which the user can download.



Security Considerations

XOR Encryption:
The current implementation uses a simple XOR cipher for encryption. While this offers a basic level of protection through obfuscation, it is not robust against determined attackers. For stronger security, integrating a standard encryption algorithm (e.g., AES) is recommended.

Usage Note:
This tool is best suited for educational purposes, low-risk obfuscation, or bypassing file-type restrictions rather than securing highly sensitive data.




## LICENSE
[MIT LICENSE](LICENSE)
