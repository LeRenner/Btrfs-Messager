# Btrfs Messager
This script allows you to periodically check the status of the disks of a btrfs array, and it sends you a message on telegram if it detects any errors. It can also send you messages in case of no errors detected, and even create an empty file on your home as an additional warning. The messages are easily customizable to your needs.

## How it works
This script periodically checks your array disks for errors as mentioned before. In case any were detected, it sends you a message on telegram warning you about that error. If it encounters an error in sending you a message it will output a message to stdout, which should send you an email if you're running this in a crontab. Optionally, you can configure it to create a file on your home (with details on which drive had the error) every time an error is detected, regardless of if it was successfull in sending you a warning message on telegram.

## Requirements
You will need a bot on telegram. The process to create one is very simple, and you can find documentation regarding it on https://core.telegram.org/bots. After that, simply create a conversation between you and your bot, and take note of the chatID of that conversation.
You also will need the token from your bot.

## Installation
Simply clone this script to a directory on your machine, and make crontab run it on the frequency you prefer. 

## Configuration
On the beguinning of the script, you need to customize certain variables to your needs. Here are their descriptions:

    btrfsArray > List with paths to your btrfs arrays
    bot_token > The token from you telegram bot
    bot_chatID > The ID of your conversation with your bot

    btrfsErrorFilePath > Full path of the file created if an error is detected on your btrfs array, and alsoSpamHome = True

    resetStatsWhenError > (Boolean) If the device stats should be reset after reading them (so you don't keep getting messages after an error is found)
    alsoSpamHome > (Boolean) If the script should create a file on your home when an error is detected, even if a message is successfully sent on telegram
    sendOkMessages > (Boolean) If the script should message you when no errors were detected
    btrfsOkMessage > Message sent if no error is detected on your btrfs array and sendOkMessage = True

## Disclaimer
This script was created for educational purposes and I can not guarantee you it works perfectly. Please use it on your own risk.


