## Deploy on VPS or PC.
- You need to Install git,ffmpeg,curl,nodejs,yarn with pm2 
   1. Install git ffmpeg curl 
      ```
       sudo apt -y update &&  sudo apt -y upgrade 
       sudo apt -y install git ffmpeg curl
      ```
   2. Install nodejs 
      ```
      sudo apt -y remove nodejs
      curl -fsSl https://deb.nodesource.com/setup_lts.x | sudo bash - && sudo apt -y install nodejs
      ```

   3. Install yarn
      ```
      curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add - 
      echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
      sudo apt -y update && sudo apt -y install yarn
      ```

   4. Install pm2
      ```
      sudo yarn global add pm2
      ```

   5. Clone Repo and install required packages
      ```
      git clone https://github.com/SamPandey001/Secktor-Md
      cd Secktor-Md
      yarn install --network-concurrency 1
      ```

   6. Create an env file for ENV. 
      ```
      touch config.env
      nano config.env
      ```
      copy paste lines below.

      ```
      OWNER_NUMBER="94729493354"
      MONGODB_URI="mongodb+srv://*************"
      SESSION_ID = "𝙌𝙐𝙀𝙀𝙉-𝙉𝙄𝘾𝙆𝙔-𝙈𝘿;;;eyJub2lzZUtleSI6eyJwcml2YXRlIjp7InR5cGUiOiJCdWZmZXIiLCJkYXRhIjoic1B2SFAvRkE0M3NtYVoyUGx0SjdXeEp4NEt5S2NLSGZJQ0FWczNHYVlWaz0ifSwicHVibGljIjp7InR5cGUiOiJCdWZmZXIiLCJkYXRhIjoiU3NSbm5zYS9UWlFhYXUvODBtNnUrZnVZUWpjaE5IWVh1bVozUWhhQTZqaz0ifX0sInNpZ25lZElkZW50aXR5S2V5Ijp7InByaXZhdGUiOnsidHlwZSI6IkJ1ZmZlciIsImRhdGEiOiI4RXBGSFRkejhMUE1ud1VpSDRKTXVTQ3I2SnhRTzhhTk9yakcxSEN4ZFhBPSJ9LCJwdWJsaWMiOnsidHlwZSI6IkJ1ZmZlciIsImRhdGEiOiIyS2IzUzVGeDNRZStIOHhNaW14VktjMkdnODdEVm5oWmd2Z0FNWXpiSmlJPSJ9fSwic2lnbmVkUHJlS2V5Ijp7ImtleVBhaXIiOnsicHJpdmF0ZSI6eyJ0eXBlIjoiQnVmZmVyIiwiZGF0YSI6IlNMRDVzTHMwaEtaTTZ0Vm5jL0dQcDVRaEhoTkV6TVg5UVFuem9nYlFMVms9In0sInB1YmxpYyI6eyJ0eXBlIjoiQnVmZmVyIiwiZGF0YSI6IlpFSy9WdVl1ZmZTS3BoWDBVQmJpWjQ5YmdsbGdMbWdIeTRoTm9JaHhJalE9In19LCJzaWduYXR1cmUiOnsidHlwZSI6IkJ1ZmZlciIsImRhdGEiOiJuT0Njakx3SEJkRjdIVGFGY0QrSWh3eGFHcDFlQnVRWFY0NktieHN6clNxWTBDYlFpclFzY1FYS04ra2I0SUR6K25sYW9IVE5rMWNFTzEzMm1XRENEdz09In0sImtleUlkIjoxfSwicmVnaXN0cmF0aW9uSWQiOjczLCJhZHZTZWNyZXRLZXkiOiJld1U2Y204NTROenJZSVlJSnU2MjFiR3hlNWxzWUNNRjdZOUhJYUVkTFJ3PSIsInByb2Nlc3NlZEhpc3RvcnlNZXNzYWdlcyI6W10sIm5leHRQcmVLZXlJZCI6MzEsImZpcnN0VW51cGxvYWRlZFByZUtleUlkIjozMSwiYWNjb3VudFN5bmNDb3VudGVyIjowLCJhY2NvdW50U2V0dGluZ3MiOnsidW5hcmNoaXZlQ2hhdHMiOmZhbHNlfSwiZGV2aWNlSWQiOiJIYUU1RmplNVRxQ2Vfd0stbDQtdWVnIiwicGhvbmVJZCI6ImJkZGExNDVmLTBhZDMtNGFhNS1hYjgzLTNjYjViNzRkMjQ0MyIsImlkZW50aXR5SWQiOnsidHlwZSI6IkJ1ZmZlciIsImRhdGEiOiJJN01OcEZwQXB2R1M0aGFmbGI0TFpxblREZzA9In0sInJlZ2lzdGVyZWQiOmZhbHNlLCJiYWNrdXBUb2tlbiI6eyJ0eXBlIjoiQnVmZmVyIiwiZGF0YSI6IkxQMXFsajZIZmdYaE5teEw2WVo3cjdOQ0VQcz0ifSwicmVnaXN0cmF0aW9uIjp7fSwiYWNjb3VudCI6eyJkZXRhaWxzIjoiQ0xySytLWUVFUHZyaGJNR0dBa2dBQ2dBIiwiYWNjb3VudFNpZ25hdHVyZUtleSI6ImVRU1VoQkJvS1l2RUxiV09TMFpHUWtFTlVjbDNEL00zbUVEcEFXcVFOWGM9IiwiYWNjb3VudFNpZ25hdHVyZSI6IitPU2oySC9LR2tvYWZDYnMzdE1CYzV5ZE55L0M1cjZqYVRZSXNOZzJXZ21LTmV3bFRRekZBNUpsMTZEWmhlSlB4Nk9COWRCZVZIQ3cvNTBNRzRockRRPT0iLCJkZXZpY2VTaWduYXR1cmUiOiJxWjlNdEUyNmdWeHhYbnNId0NiQjNsQ1dmR2FSSExCUnl2UnViUGh5aHRpc091ang1NU0yOVUrYU8zY2FsY3BRMFovVkRzcC8wKzJhbzdSbmRBR0VBQT09In0sIm1lIjp7ImlkIjoiOTQ3Mjk0OTMzNTQ6ODJAcy53aGF0c2FwcC5uZXQifSwic2lnbmFsSWRlbnRpdGllcyI6W3siaWRlbnRpZmllciI6eyJuYW1lIjoiOTQ3Mjk0OTMzNTQ6ODJAcy53aGF0c2FwcC5uZXQiLCJkZXZpY2VJZCI6MH0sImlkZW50aWZpZXJLZXkiOnsidHlwZSI6IkJ1ZmZlciIsImRhdGEiOiJCWGtFbElRUWFDbUx4QzIxamt0R1JrSkJEVkhKZHcvek41aEE2UUZxa0RWMyJ9fV0sInBsYXRmb3JtIjoiYW5kcm9pZCIsImxhc3RBY2NvdW50U3luY1RpbWVzdGFtcCI6MTcxNzY2MzIzMH0="
      THUMB_IMAGE = "https://raw.githubusercontent.com/SecktorBot/Brandimages/main/logos/SocialLogo%201.png"
      port = 5000
      email = "sam@secktor.live"
      global_url = "instagram.com"
      OWNER_NAME = "SamPandey001"
      AUTO_REACTION = false
      FAKE_COUNTRY_CODE = 92
      READ_MESSAGE = false
      PREFIX = .
      WARN_COUNT = 3
      DISABLE_PM = false
      ANTI_BAD_WORD = "fuck"
      LEVEL_UP_MESSAGE= true
      WELCOME_MESSAGE =  "*Hi,* @user \n*Welcome in* @gname \n*Member count* : @count th"
      THEME= SECKTOR
      WORKTYPE = public
      PACK_INFO = "Sam;Pandey"
      ANTILINK_VALUES = "chat.whatsapp.com"
      
      ```
      ctrl + o and ctrl + x, To save and exit

   7. start and stop bot

      To start bot ``` npm start ```,
      To stop bot ``` npm stop ```
