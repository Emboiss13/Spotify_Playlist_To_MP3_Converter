# 🎧 Spotify Playlist to MP3 Downloader + MP3 Tag Editor
This project helps you convert your private Spotify playlists into MP3 files by searching for matching videos on YouTube and downloading the audio. It also includes a separate script to batch-edit MP3 metadata (album, artist, genre, etc.), perfect for organising your files for an MP3 player.

**Why did I decide to do this project?**
I was manually downloading my Spotify playlists into an MP3 player, and it was getting too tedious 🤭. So I thought hmmm... maybe I can automate this, and it went well! 

### 📁 Project Structure
- **SpotifyPlaylistReader.py**  _→ Script to extract songs from Spotify and download them as MP3s_
- **MP3TagEditor.py**           _→ Script to edit tags (album, artist, genre) of MP3 files_

### ⬇️ Prerequisites
Make sure you have these installed:

1. Python 3.9+
2. Install Python packages:
`pip install spotipy yt-dlp mutagen`
https://spotipy.readthedocs.io/en/2.22.1/#getting-started
4. Install FFmpeg (required by yt-dlp for MP3 conversion).
- **For macOS (with Homebrew)**:
`brew install ffmpeg`
- **For Windows**:
Download FFmpeg from https://ffmpeg.org/download.html and add it to your system PATH.


---
### Script 1: SpotifyPlaylistReader.py

**What it does:**
- Authenticates with your Spotify account
- Lists your playlists
- Let's you choose one playlist to download
- Fetches the song titles and artists
- Searches for each track on YouTube
- Downloads the best audio and converts it to MP3

<br>

**You will need:**
- A Spotify Developer App → [ClientID & ClientSecret](https://developer.spotify.com/documentation/web-api/concepts/apps)
  - playlist-read-private scope
  - Redirect URI set to: http://127.0.0.1:8888/callback
  - You'll be prompted to log in to Spotify the first time.
 <br>
 <img width="2768" height="776" alt="image" src="https://github.com/user-attachments/assets/304f63a5-df57-4124-957d-8cf4c3433b80" />


<br>
<br>

**Changes you MUST make to the code**: 
>**IMPORTANT❗️:** _Change `CLIENT_ID = 'id'` and `CLIENT_SECRET = 'secret'` in the 🔓 authentication section, to match your Spotify Developer Credentials._

<br>

Change `line 115` to match the path you want to download the songs to: 
```python
def download_as_mp3(youtube_url, song_name, output_folder='[ADD YOUR PATH HERE]'):
    safe_filename = clean_filename(song_name)
```

*Example:*
```python
def download_as_mp3(youtube_url, song_name, output_folder='/MyWindowsPC/Downloads'):
```

<br>


### ▶️ How to run:
Open a terminal in the folder where you've cloned this repo and run `python3 SpotifyPlaylistReader.py`

<br>

---
### Script 2: MP3TagEditor.py

<br>

**What it does:**
- Edits the metadata tags of all .mp3 files in a given folder
- Supports adding album name, artist, and genre
- Keeps things organised for MP3 players and music libraries

<br>

### ▶️ How to run:
Open a terminal in the folder where you've cloned this repo and run `python3 MP3TagEditor.py`

<br>

You'll be prompted to:
- Enter a folder path with your MP3s
- Optionally enter album, artist, and genre names

<br>

---
#### Legal & Ethical concerns:
- These scripts do not upload or re-host any copyrighted content.
- Always check YouTube’s and Spotify’s terms of use.
- **This project is intended for personal use only.**

---
Author: Giuliana E — frontend developer exploring Python 
