UserBot - Telegram Userbot for Message Filtering and Auto Responses
This UserBot is a Telegram bot built using the Telethon library that monitors private messages. It automatically responds to certain keywords, deletes offensive words, and interacts with users based on predefined patterns. It is designed for personal use to help manage interactions on Telegram.

Features:
Message Filtering: Automatically deletes messages containing offensive words defined in sokinish.txt.
Automatic Replies: Responds to common greetings, queries, and commands like "salom" (hello), "kitob" (book), and more.
File Responses: Replies with files when specific keywords are detected (e.g., when "kitob" is mentioned).
Online Check: Ensures the bot only responds when the user is offline.
Requirements
Before running the bot, make sure you have the following:

Python 3.7 or higher.
Telethon: A Python library to interact with the Telegram API.
Telegram API credentials: You need an API ID and API hash.
Sensitive words list (sokinish.txt) for offensive word detection.
Setup Instructions
1. Clone the Repository
Clone the repository to your local machine:

bash
Копировать код
git clone https://github.com/yourusername/userbot.git
cd userbot
2. Install Required Packages
Ensure that you have Python 3.7 or higher installed. Then install the necessary dependencies using pip:

bash
Копировать код
pip install telethon
Or, create a requirements.txt file:

txt
Копировать код
telethon
And install the dependencies:

bash
Копировать код
pip install -r requirements.txt
3. Get Telegram API Credentials
To use Telethon, you need to obtain API ID and API Hash from Telegram.

Visit Telegram API development tools.
Log in with your Telegram account and navigate to API development tools.
Create a new application to get your API ID and API Hash.
4. Configure the Bot (config.py)
Create a config.py file in the conf folder (create the folder if it doesn't exist). This file should contain your API credentials and phone number.

Example (config.py):

python
Копировать код
api_id = 'your_api_id'  # Replace with your Telegram API ID
api_hash = 'your_api_hash'  # Replace with your Telegram API Hash
phone_number = 'your_phone_number'  # Replace with your phone number (including country code)
5. Prepare the Offensive Words List (sokinish.txt)
Create a file named sokinish.txt in the same directory as the script. This file should contain a list of offensive words, one per line.

Example (sokinish.txt):

Копировать код
badword1
swearword2
offensive_term
The bot will check each incoming private message against this list and delete any message containing these words.

Running the Bot
1. Start the Bot
To start the bot, simply run the userbot.py script:

bash
Копировать код
python userbot.py
The bot will:

Start the Telegram client and monitor incoming private messages.
Check each message for offensive words from the sokinish.txt file.
Automatically respond to certain keywords with predefined responses.
Reply with a file when the word "kitob" (book) is mentioned.
Send responses for greetings, questions, and other specified phrases.
2. Customize the Bot Responses
You can customize the responses by modifying the following variables in userbot.py:

salom: List of greetings like "salom" and "hello".
xol: List of words like "yaxshi", "qanday", and "qale" that trigger responses about the user's well-being.
chaqirish: List of words like "ustoz", "domla", and "teacher" that trigger responses to address the user.
link: Words like "http://" and "https://" to detect and reject links in messages.
Add more keywords or modify existing ones to suit your needs.
3. Stop the Bot
To stop the bot, press Ctrl + C in your terminal.

How It Works
Offensive Word Detection: The bot reads words from the sokinish.txt file and checks each incoming private message against this list. If an offensive word is found, the message is deleted, and a warning is sent.

Automatic Responses: The bot listens for certain words or patterns:

"kitob": Sends a file (e.g., python asoslari).
"salom", "hello": Sends a greeting message.
"yaxshi", "qanday", "qale": Responds to inquiries about well-being.
"ustoz", "domla": Responds to teacher-related queries.
User Online Status: The bot only processes and responds to messages when the user is offline. It checks the online status and responds accordingly.

Session Handling: The bot uses an SQLite session to maintain its connection with Telegram, ensuring smooth operation even after disconnects.

License
This project is open-source and licensed under the MIT License.

Troubleshooting
Here are some common issues and solutions:

API Credentials: Ensure that your api_id and api_hash are correct in config.py.
Dependencies: If you encounter errors with missing modules, install the dependencies via pip install -r requirements.txt.
File Permissions: Make sure the bot has the necessary permissions to read the sokinish.txt file.
Conclusion
This userbot is a great example of how to build a Telegram bot that can monitor and respond to private messages, delete offensive content, and automate responses. You can further expand its functionality by adding more features or modifying the existing ones.

Feel free to contribute or ask questions!

