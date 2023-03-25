# Developer Guide

This guide is intended for developers who want to contribute to the project. It is not intended for users who want to use the project.


## Getting Started

Clone the cloak repository:
```bash
git clone https://github.com/cloak-dev/cloak
```

Clone the docs repository:
```bash
git clone https://github.com/cloak-dev/docs
```

## Environment

Any modern browser should work. In particular, the WebCrypto API must be available.

## How end-to-end encryption works
Read our blog post on [how end-to-end encryption works](https://cloak-dev.github.io/blog/eli5-how-e2ee-works/).

## How Cloak Works

The core of Cloak is the `E2EE` class, which is responsible for maintaing key-pairs, and provides methods to perform [ECDH](https://en.wikipedia.org/wiki/Elliptic-curve_Diffie%E2%80%93Hellman), as well as [AES-CTR](https://en.wikipedia.org/wiki/Block_cipher_mode_of_operation#Counter_(CTR)) encryption and decryption.

The `Cloak` class is then responsible for hooking into the chat application, and using the `E2EE` class to encrypt and decrypt messages.

Hooking into the chat application goes two ways:

1. Hooking into the "send" button, and encrypting the message before it is sent.

2. Hooking into the websocket connection, and decrypting the message before it is displayed.

You may ask, how does key exchange happen? Do the users need to do it manually out of band?

No! The key exchange is handled by cloak itself using the message hooking mechanism itself. This is received by the cloak instance in the receivers end, and the key exchange is completed.

## How to Contribute

If you want to contribute to the project, you can do so by:
1. Opening an issue on the [cloak repository](https://github.com/cloak-dev/cloak).
2. Adding support for a new chat application. (see below)
3. Contributing to the [documentation](https://github.com/cloak-dev/docs)
4. Contributing to the [blog](https://github.com/cloak-dev/blog)

## Adding support for a new chat application.

To add support for a new chat application, you need to do the following:

1. Create a new file in the `usecases` directory, and name it after the chat application. For example, if you are adding support for Discord, you would name the file `discord.ts`.
2. Write a hook that hooks into the chat application's "send" button, and encrypts the message before it is sent using the `E2EE` class. You can use the `usecases/basic.ts` file as a reference.
3. Write a hook that hooks into the chat application's websocket connection, and decrypts the message before it is displayed using the `E2EE` class. You can use the `usecases/basic.ts` file as a reference.
4. Test your code, using the test chat server provided.
5. Open a pull request.


## Note
The core of Cloak is closed to contributions. This is because we want to ensure that the core of Cloak is secure, and we don't want to compromise on that. However, we are open to contributions to the chat application hooks, and the documentation.


