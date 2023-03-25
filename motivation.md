# Motivation

## What is end-to-end encryption?

End to end encryption is a method of encrypting data so that only the sender and the receiver can read it. This is in contrast to encryption that is done by a third party, such as a server or a cloud storage provider. In messaging apps, this means that only the sender and the receiver can read the messages that they send to each other, and only the encrypted messages are stored on the server.

## What is the problem with end-to-end encryption?

Most messaging apps have end-to-end encryption, but are closed source. This means that you cannot verify that the encryption is actually being used. There are famously instances of popular messaging apps like Skype, WhatsApp, and Facebook Messenger being caught using insecure encryption, or not using encryption at all, and providing governments backdoors to read messages. This is a huge problem, as it means that your messages are not secure, and can be read by anyone who has access to the servers.

## Well, the government can read it anyway if they take my phone from me, so why bother?

The problem isn't exactly the state reading your messages. The fact that there is a backdoor means that the message has to be processed in plaintext by the chat server. This opens the possibility of anyone, not just the government reading your messages just by attacking the chat server. This is a huge problem, as the security of your messages now rests fully on the security of the chat server, which is a single point of failure. If the chat server is compromised, then all of your messages are compromised.

## What is the solution?

The solution is simply to use your _own_ layer of end-to-end encryption. Essentially, you don't trust that the messaging app actually encrypts your message, and you encrypt it first _before_ even giving the message to the app. This means that the app can't read your messages, and so if it is ever passing the un-encrypted message to the server, it will still be encrypted with the first process.

## Encryption and decryption is way too complicated, how does this scale to a solution that the average person can use?

This is where Cloak comes in. Cloak is a plugin for any web-based messaging app that automatically encrypts your messages before sending them to the server. This means that you can use any messaging app that you want, and still have the security of end-to-end encryption. This is a huge step forward in the security of messaging apps, as it means that you can use any messaging app that you want, and still have the security of end-to-end encryption.

## Well, this just seems like kicking the can down the road. What if Cloak itself has a backdoor?

This is a valid concern, and one that we take very seriously. To that end, all of our code is open-source, and it runs entirely in your web browser. There is no "cloak server" to which your messages can be sneakily passed to!

## So, is it actually a silver bullet?

Almost. You just have to make sure you always procure cloak from the official website. If you download it from anywhere else, it may be malicious.
