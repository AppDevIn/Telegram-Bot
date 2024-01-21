# TelegramBot

## Project Description

This project uses the telegram bot API to create a bot service

## Installation

To install with pip <br>

```
$ pip install Telegram-Bot8
```

## Usage

```python
import os

from TelegramBot8 import Message, TeleBot, ParseMode, Update, BotCommandScope, MediaResponse, Error, BaseResponse, \
    InlineKeyboard, InlineKeyboardButton, CallBackQuery, ReplyKeyboard, ReplyKeyboardButton

API_KEY = os.getenv('env_variable_name')
bot = TeleBot(API_KEY)

@bot.add_command_helper(command="/hi")
def hi(message: Message):
    bot.send_message(message.chat.getID(), "Hello")


@bot.add_command_menu_helper(command="/bye", description="Just testing added command")
def bye(message: Message):
    bot.send_message(message.chat.getID(), "Bye")


@bot.add_regex_helper(regex="^hi$")
def regex(message: Message):
    bot.send_message(message.chat.getID(), "Hello")

bot.poll()
```

## License

Distributed under the MIT License. See `LICENSE` for more information.

