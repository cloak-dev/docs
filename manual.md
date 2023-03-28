# User Manual

## Introduction

This is the user manual for the [Cloak](./index.md) application, an end-to-end encryption layer on top of any web-based chat application.

## Installation

See the [installation instructions](./index.md#install).

## Usage

### Starting the application

Once you have loaded a [supported chat application](./index.md#supported-chat-applications), simply click the Cloak extension's button.

<img src="https://i.imgur.com/gNJn1mY.png">

### Chatting

Get your friend to perform the same steps you did above. Cloak needs to be set up on both ends of the conversation. Your screens should both look like this:

<img src="https://i.imgur.com/JV5S5ds.png">

Once the both of you are done, click the 'Start Encrypting' button in the top right of your screen to start the encryption layer. You will see a Cloak logo replace the button to indicate that the encryption layer is active.

<img src="https://i.imgur.com/gTET5ks.png">

You will also see a seemingly garbled message appear in the chat window. This is normal. It is the setup message that your friend's instance of Cloak sent to your's. Your friend will see a similar message in their chat window.

<img src="https://i.imgur.com/DgQGnQB.png">

All future messages however, will appear to you in plain text. However, the server will simply see a bunch of garbled text!

### Session Management

Everytime you close or reload the tab, the encryption layer will be reset. This is to prevent any potential security issues. Next time you open the app, you will have to repeat the process to enable the encryption layer.

### Uninstall

To uninstall Cloak, simply remove the extension.

<img src="https://i.imgur.com/wLXdqhs.png">
