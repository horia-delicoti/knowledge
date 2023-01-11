# Cybersecurity

- [TryHackMe](https://tryhackme.com)

## Tools
- [Amazing Security Tools](https://github.com/eugenekolo/sec-tools)
- [Some setup scripts for security research tools](https://github.com/zardus/ctf-tools)

# Steganography

Steganography is a way of hiding a secret message inside something. For example hiding secret within a image or audio file.

- [Steganography - A list of useful tools and resources](https://0xrick.github.io/lists/stego/#steghide)
- [Understanding Steganography and how it work](https://gupta-bless.medium.com/understanding-steganography-and-how-it-work-63593ddba21e)
- [Understanding Steganography for Capture The Flag Challenges](https://infosecwriteups.com/steganography-ctfs-73f7b310b1f7)

## Useful Commands for [Steghide](https://github.com/StefanoDeVuono/steghide)

```sh
# install steghide
apt-get install steghide
```

```sh
# displays info about a file whether it has embedded data or not.
steghide info <file>
```

```sh
# embed file secret_text.txt into the file image.jpeg
steghide embed -cf image.jpeg -ef secret_text.txt
```

```sh
# extract embeded data from file image.jpeg
steghide extract -sf image.jpeg
```