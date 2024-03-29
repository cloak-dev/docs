# Cloak

## What is cloak?

Cloak is a simple, lightweight, **purely client-side**, browser script that allows you to end-to-end encrypt your messages on all major web-based chat applications. It is designed to be easy to use. Cloak is currently in beta, and is not yet ready for production use.

## Why do I need Cloak?

As an avid internet user, you are sure to be using a variety of web-based messaging apps. Some, like WhatsApp, are so ubiquitous in our daily lives. In all the furore, what is sometimes lost is that the corporations running those apps may not always have your best interests in mind. One of the major ways they can exploit your activities is by collecting and analyzing your messages. Although they claim to encrypt your message, no one can verify that and messaging apps like Skype have been previously caught reading your messages behind your back. Cloak, let's you _guarantee_ encryption, while letting you continue using whatever messaging app you already use!
Read the [motivation](motivation.md) for more information.

## Features

-   End-to-end encryption
-   [Open source](https://github.com/cloak-dev)
-   One-click setup

## Supported Chat Applications

-   [Our test server]() (Deployed)
-   [Whatsapp](https://web.whatsapp.com/) (Beta)
-   [Jitsi Meet](https://meet.jit.si/) (Testing)
-   [Google Meet Chat](https://meet.google.com/) (Alpha)

Want to add support for another chat application? [Read the developer guide](developer-guide.md).

## Install

You can install Cloak on Google Chrome as a Chrome Extension as well as on Firefox as a Firefox addon.

## Getting Started

First, you and your friend need to [install Cloak](#install). Once you both have installed Cloak, you can open a [supported chat application](#supported-chat-applications), and simply click on the extension, and then click on the 'Start encrypting' button that appears. Once the both of you have done this, simply click the Cloak logo that appears on the top right of your screen.

And that's it! All future messages between the both of you in that chat application will be encrypted for the current session. If you reload the tab, you will have to run the script again.

For more detailed instructions, see the [manual](manual.md).

## Developers

If you want to learn more about how cloak is built, contribute to it by e.g adding support for another chat application, see the [developer guide](developer-guide.md).

## FAQ

<details>
<summary>My chat application already has end-to-end encryption. Why do I need Cloak?</summary>
Most chat applications have end-to-end encryption, but are closed source. This means that you cannot verify that the encryption is actually being used. Cloak is open source, so you can verify that your messages are actually being encrypted. [Countless times](https://cloak-dev.github.io/blog/e2ee-backdoors), closed-source chat applications have been caught using insecure encryption, or not using encryption at all. See [motivation](motivation.md) for more information.
</details>
<details>
<summary>
How does Cloak work?
</summary>
A shared key is arrived at using the ECDH key exchange, and is used to encrypt and decrypt messages. The shared key is never sent over the network, and is only stored in the browser's memory. The shared key is destroyed when the tab is closed.

All messages are sent by hooking into the "send" button of your chat app, and all messages are received by hooking into the websocket connection of your chat app.

There is no Cloak server involved; everything happens entirely in the browser.
</details>
<details>
<summary>
How secure is Cloak?
</summary>
Cloak uses the battle-tested WebCrypto API, which is used by many other secure applications. The encryption is done using AES-GCM with ECDH, which is the same suite WhatsApp claims to use in their application. For Cloak however, these claims are verifiable, as the code is open source.
</details>
<details>
<summary>
How does Cloak compare to other end-to-end encryption solutions?
</summary>
As far as we are aware, there is no product that matches up to Cloak in terms of ease of use, feature-set, security, and openness. However, there are many products adjacent to this space that Cloak draws inspiration from, such as Cryptomator, a ZK encryption product. We have a [blog post](https://cloak-dev.github.io/blog/cryptomator-zk-encryption) about the same as well.
</details>
<details>
<summary> Why isn't cloak available on the mobile platform? </summary>
Cloak requires hooking into various functionalities of the chat application, which is not possible on mobile where each application runs in it's own isolated environment. So, atleast for now, Cloak is available only on the web.
</details>
<details>
<summary> My browser is not supported. What do I do? </summary>
Cloak makes extensive use of the WebCrypto API, which is available only on major browsers post 2017. Older browsers simply **cannot be supported** by Cloak, as it would mean using a non-standard polyfill for WebCrypto, which would be a security risk, or would mean adding an external dependency, which would open Cloak to supply chain attacks. Cloak would also be slower on older browsers, as it would have to run the full encryption algorithm in the browser, instead of using the native WebCrypto API.
</details>
<details>
<summary> This all seems very interesting. Where can I delve into the details? </summary>
If you are a developer, you can read the [developer guide](developer-guide.md). If you are a user, you can read the [manual](manual.md).

For general reading about end-to-end encryption and security, check out our [blog](https://cloak-dev.github.io/blog/)!.
</details>