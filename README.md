# Tidal-DL-Bot-TG

Telegram bot to download Songs from Tidal.

## Features

- Download Tracks/Albums/Mix/Playlist from Tidal
- Quality available upto Master-FLAC
- Search songs inline using Tidal-API
- Store downloaded songs to Channel/Group
- Bot can configured for Public or Private use
- Index Channel Feature for avoiding duplicate and search option
- Auto convert other music platform link to Tidal link 

**⚠️ Download Feature Won't Work Without A Tidal Premium Account ⚠️**

## Variables Details

**-> Required Variables**

- `TG_BOT_TOKEN` - The Telegram Bot Token. (Get from [@BotFather](https://t.me/BotFather))
- `APP_ID` - Telegram account API ID. (Get it from [Telegram](https://my.telegram.org))
- `API_HASH` - Telegram account API HASH String. (Get it from [Telegram](https://my.telegram.org))
- `AUTH_CHAT` - List of Chat ID where Bot will work. (Seperated by space)
- `ADMINS` - List of User ID who has full access to the Bot. (Seperated by space)
- `ALLOW_DUMP` - Whether to store the downloaded files in any group/channel. (True/False)
- `IS_BOT_PUBLIC` - Whether to allow bot usage for public. (True/False)
- `TIDAL_REGION` - Country code for Tidal Song search. (In international format eg:IN)
- `TIDAL_SEARCH_LIMIT` - Limit the number of search results.
- `BOT_USERNAME` - Username of your bot.
- `DATABASE_URL` - Postgres Database URL (Get it from [Elephantsql](https://www.elephantsql.com/))


**-> Optional Variables**

- `LOG_CHANNEL_ID` - Group/Channel ID where bot stores all the downloaded files (Mandatory if set ALLOW_DUMP = True)
- `AUTH_USERS` - List of User ID who can use the bot (Seperated by space) (Only needed if IS_BOT_PUBLIC = False)
- `INLINE_THUMB` - Logo to be shown in inline search results. (Use CDN links for better performance)
- `ENV` - Set to True if using ENV Variables.
- `SEARCH_CHANNEL` - ID of channel/gropup to search downloaded/other songs files direcly
- `USER_SESSION` - Telegram account session string. (Required for Searching and Indexing to work) (Generate from [HERE](https://replit.com/@vm703/Pyro-Session-Gen?lite=1&outputonly=1#main.py) or use any other Pyrogram Session Generator)
- `MUSIC_CHANNEL_LINK` - For providing direct join link to the Music Storage Channel while searching for songs inline.
- `ALLOW_OTHER_LINKS` - If to allow automatic conversion of other music platform links to Tidal links while downloading. (Current API has a limit of 10 conversion per minute) (True/False)

```
start - Start the bot
help - Shows Help Message
download - Download songs from Tidal
auth - Authorise a chat/user
settings - Open Settings Panel [ADMIN ONLY]
add_sudo - Add a user as Admin [ADMIN ONLY]
shell - Run shell cmds [ADMIN ONLY]
index - Index Search channel with Songs [ADMIN ONLY]
authed - Shows list of chats where bot is allowed to run
```
## Deploy VPS METHOD-1

Change.env add variable

## Add New Screen

```
sudo apt install tmux
tmux ls
tmux new -s session_name
tmux a -t session_name
tmux kill-session -t session_name

```

```

sudo apt install python3-virtualenv

virtualenv -p python3 VENV

. ./VENV/bin/activate

pip install -r requirements.txt

pip install psycopg2-binary 

python -m bot

```
- For Database URL use Heroku Postgres (if on Heroku) or ElephantSQL

## Deploy VPS METHOD-2 (STABIL) AND BASIC

- Start Docker daemon (skip if already running), if installed by snap then use 2nd command:
    
        sudo dockerd
        sudo snap start docker

     Note: If not started or not starting, run the command below then try to start.

        sudo apt install docker.io

- Build Docker image:

        sudo docker build . -t tidal-dl-bot

- Run the image:

        sudo docker run tidal-dl-bot

- To stop the image:

        sudo docker ps
        sudo docker stop id

- To clear the container:

        sudo docker container prune

- To delete the images:

        sudo docker image prune -a
