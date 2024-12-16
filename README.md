# TELEGRAM THE ULTIMATE SOURCE OF OSINT
---
![tele](https://github.com/user-attachments/assets/999a8688-267b-4853-8fc5-cb6a0ce3b53d)

---
## About the Repository

This repository provides a comprehensive collection of tools, guides, and resources for conducting Open Source Intelligence (OSINT) investigations using Telegram. It includes tools for analyzing chats and channels, bots, browser extensions, and custom search engines. With a strong focus on OPSEC, it also offers tips on secure practices like using VPNs, virtual machines, and disposable devices. The repository is ideal for researchers and investigators aiming to uncover information efficiently and securely on Telegram.

Explore the structured sections, including Google dorks, blogs, and even video tutorials, making it a go-to resource for mastering Telegram OSINT.

---

## Table of Contents
1. [Analyzing Telegram chats and channels](###Analyzing-Telegram-chats-and-channels.-Regular-expressions-in-OSINT-in-practice)
1. [Telegram Resources](#telegram-resources)
2. [Blogs](#blogs)
3. [Browser Extensions](#browser-extensions)
4. [Tools and Resources](#tools-and-resources)
5. [Telegram Bots](#telegram-bots)
6. [Custom Search Engines](#custom-search-engines)
7. [Google Dorks](#google-dorks)
8. [YouTube Playlists](#youtube-playlists)
9. [Videos](#videos)

---


### Analyzing Telegram chats and channels. Regular expressions in OSINT in practice 

Reading other people’s conversations in public Telegram chats can sometimes be very boring and tedious. And unfortunately, often it may not yield any results.
But sometimes people inadvertently leave various personal data in public groups that can greatly advance an investigation: emails, links to their social networks and sites, real names and surnames, phone numbers, and much more.

## How to know which group chats a person is communicating in

![App Screenshot](https://miro.medium.com/v2/resize:fit:828/format:webp/1*eGtWkyF0uJ-GsTAZGFmCtw.png
)

There are a lot of bots in Telegram that use the username to find out which groups a user has joined. Most of them are paid, but as a test they offer the opportunity to make a couple of requests for free. For example

```markdown
https://t.me/tgdb_bot
https://t.me/FaizanBreachBot
```

Such bots are quite a lot and you can find them on your own in directories or with the help of Telegram search engines.

The effectiveness of the bot depends on the number of indexed groups in its database. And different bots produce different results (because they have different databases of indexed groups).

Therefore, it is better to check one user in several bots at once.

You can also search by username in Telegram search engines like https://lyzem.com/, but this does not always yield any results (and always shows only a small fraction of the chats in which the user participates).

![App Screenshot](https://miro.medium.com/v2/resize:fit:828/format:webp/1*zw-lejuJbJCF9dganSCD0w.png)

Therefore, it is worth trying different methods. It is also worthwhile to search for a user’s nickname in Google, as well as other services for Telegram searches, which I will discuss in the next section.

### How to find Telegram chats by keywords


Another way to find in which group chats a person communicates is to simply check each chat related to his profession, hobby, location (public group of a neighborhood or an apartment complex), etc.

![App Screenshot](https://miro.medium.com/v2/resize:fit:828/format:webp/1*zw-lejuJbJCF9dganSCD0w.png)

You can do it with any Telegram search engines. You can find a list of them in my collection, but I prefer Teledago more than any other.

This service is based on Google Custom Search Engine technology. It searches through dozens of domains at once, which are indexed by data from Telegram:

```Tgstat; Telegramindex; Telegramdb;Telemetr; and more``` 

To search only for chats, add “inurl:chat” to the search query

### How to export Telegram chat history
![App Screenshot](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*DN8QqUxPsyYyoqVtl9FHiw.png)

- Open the Windows or MacOS version of Telegram client on your computer (the Linux version most likely also has this function, but I haven’t checked).
- Click on the three dots in the upper right corner of the screen.
![App Screenshot](https://miro.medium.com/v2/resize:fit:828/format:webp/1*kgoUqITRZOu7e09Y7XWwqw.png)

- Click “Export chat history”.
- Be careful when configuring chat export settings. If the chat is large, don’t forget to increase the file size limit to the maximum (assuming you have free space on your hard drive).
-  Click export and wait.

![App Screenshot](https://miro.medium.com/v2/resize:fit:828/format:webp/1*f_jojBvxkyFUrzZk97Pr9g.png)
- When a message appears telling you that the export is complete, click “Show my data” to open the folder with the result’s files.
![App Screenshot](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*W4jyse_NLfV-c5IETuDmQA.png)

- That’s it! Now you can open files in a browser or text editor and analyze them.

***Just in case, let me remind you that in Telegram, you can export the history not only of group chats, but also of conversations between two people and posts of channels.***

### Some words about other messengers

![App Screenshot](https://miro.medium.com/v2/resize:fit:828/format:webp/1*xbq26H2at12EzDM0G-xbUA.png)


It’s worth clarifying that the methods described below (with minor syntax changes) are universal and can be used to analyze not only Telegram chats, but also other popular messengers.

For example, WhatsApp has a “chat backup” function (More options > Settings > Chats > Chat backup) and Viber has “email chat history”.

There are also various third-party applications for exporting chats. Such as Signal Backup or Discordmate — Discord Chat Exporter . On Github and Chrome Web Store you can find similar solutions for a variety of messaging and social networking applications.

### What tools can be used to analyze chats

![App Screenshot](https://miro.medium.com/v2/resize:fit:828/format:webp/1*ycup96Bu0DRDW8QErA1mlQ.png)



Below I’ll show you how to examine chats for important information using Sublime Text and Google Sheets, but that doesn’t mean it’s the optimal solution.

You can also use any other text editors that support regular expressions, various command line utilities and Chrome extensions to search using regular expressions (like find+).

***In addition, you may like specialized tools for analyzing Telegram chats:***

```markdown
Splunk Telegram (visualizes data) : https://github.com/dmuth/splunk-telegram
Telegram Message Analyzer (probably a little out of date) : https://github.com/zqtay/Telegram-Message-Analyzer
Biba and Boba (finding correlations between people) : https://github.com/andylvua/bibaandboba
```

### Search for all messages from a specific person in the export results files
![App Screenshot](https://miro.medium.com/v2/resize:fit:828/format:webp/1*cUUKmsEX3YWJF5l565sBBg.png)

- Select all the files, right-click and use the context menu to open them in Sublime Text.

***If you are going to analyze several chats, then try to export each of them first, then collect all the files in one folder and open messages from all chats to be analyzed at once. This will help save time.***

![App Screenshot](https://miro.medium.com/v2/resize:fit:828/format:webp/1*waV1kdRHwRkWMbUnq7unKQ.png)

-  Click Find -> Find in files, put this regular expression to the text field and click Find:

```<div class=”from_name”>\nMatthew(.|\n)*?<div class=”body”>```

![App Screenshot](https://miro.medium.com/v2/resize:fit:828/format:webp/1*0Y2hKDT_xv4UPsSsYcJqOw.png)

Remember to replace Matthew with any username you are interested in.

-   This will open a new file with lines containing URLs from all currently open files.

-  To quickly go to the file where the link you are interested in is mentioned — just click on the line number on the left.

![App Screenshot](https://miro.medium.com/v2/resize:fit:828/format:webp/1*Y8PVsA5xP1kq7Z6pEzI9zg.png)

### Find potentially interesting information in the user’s messages

-  Click Find all

This will find all messages from a particular user that contain links to websites or accounts in Telegram.

Similarly, other potentially interesting data can be found:

Emails

```[a-zA-Z0–9.!#$%&’+-/=?\^_`{|}~-]+@[a-zA-Z0–9-]+(?:.[a-zA-Z0–9-]+)```

Phone numbers in different formats:

```markdown
[\+]?[(]?[0–9]{3}[)]?[-\s\.]?[0–9]{3}[-\s\.]?[0–9]{4,6}

Any six-digit number

\d{6}
```

Bitcoin Wallet Address

```(bc1|[13])[a-zA-HJ-NP-Z0–9]{25,39}```

Ethereum wallet address

```0x[a-fA-F0–9]{40}```

Similarly, you can find the wallet addresses of any cryptocurrency, as well as strings corresponding to many different patterns.

## Telegram Resources

| **Category**         | **Description**                                         | **Link**                                                                 |
|-----------------------|---------------------------------------------------------|---------------------------------------------------------------------------|
| Transparency Bot      | Telegram's new transparency report bot.                | [Transparency Report Bot](https://t.me/transparency)                     |
| New ToS Report        | Information on Telegram's recent Terms of Service.     | [Telegram ToS](https://telegram.org/tos)                                 |

---

## Blogs

| **Title**                                 | **Description**                                                                                       | **Link**                                                                                           |
|-------------------------------------------|-------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| Cqcore: Telegram Fundamentals             | How to set up a Telegram account and address OPSEC issues.                                            | [Read More](https://cqcore.uk/telegram-fundamentals/)                                             |
| Cqcore: Telegram VM (Part 1-3)            | Learn to build a bespoke VM for Telegram OSINT.                                                       | [Part 1](https://www.cqcore.uk/telegram-osint-vm-part-1/), [Part 2](https://www.cqcore.uk/telegram-osint-vm-part-2/), [Part 3](https://www.cqcore.uk/telegram-osint-vm-part-3/) |
| Cyber Detective: Chats & Channels         | Analyzing Telegram chats and channels with regular expressions.                                       | [Read More](https://medium.com/@cyb_detective/analyzing-telegram-chats-and-channels-regular-expressions-in-osint-in-practice-48810d5b77e6) |
| Hatless1der: Five Basic Tips              | Tips on using Google dorking and inspect element for Telegram OSINT.                                  | [Read More](https://hatless1der.com/telegram-osint-basics-5-tips-anyone-can-do-right-now/)         |
| Officer's Notes: Security Best Practices  | Best practices for Telegram security.                                                                 | [Read More](https://osintteam.blog/telegram-security-best-practices-1b33eb10be05)                 |

---

## Browser Extensions

| **Name**                 | **Description**                                                                     | **Link**                                                                                     |
|--------------------------|-------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------|
| TG Search Engine         | Find Telegram groups and channels by entering keywords.                            | [TG Search Engine](https://chrome.google.com/webstore/detail/tg-search-engine-tg-group/ilpgiemienkecbgdhdbgdjkafodgfojl/related) |
| Save Telegram Chat History | Save chat history, including photos, and works on deleted accounts.               | [Save Chat History](https://github.com/pigpagnet/save-telegram-chat-history)                |
| Telegram Sender          | Scrape user information from Telegram groups.                                      | [Telegram Sender](https://chrome.google.com/webstore/detail/telegram-sender-telegram/kchbblidjcniipdkjlbjjakgdlbfnhgh)         |

---

## Tools and Resources

| **Name**                      | **Description**                                                                                  | **Link**                                                                                   |
|-------------------------------|--------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| Awesome-Telegram-OSINT        | Curated list of Telegram OSINT tools and resources.                                             | [Awesome-Telegram-OSINT](https://github.com/ItIsMeCall911/Awesome-Telegram-OSINT)         |
| Bellingcat Phone Number Checker | Check if a specific phone number is connected to a Telegram account.                          | [Phone Number Checker](https://github.com/bellingcat/telegram-phone-number-checker)       |
| Geogramint                   | OSINT geolocalization tool for Telegram to find nearby users and groups. (Currently Not Working) | [Geogramint](https://github.com/Alb-310/Geogramint)                                       |
| TG Collector                 | Collect Telegram messages from channels via a graphical interface.                              | [TG Collector](https://www.tgcollector.com/)                                              |

---

## Telegram Bots

| **Bot Name**            | **Description**                                                                | **Link**                                |
|-------------------------|--------------------------------------------------------------------------------|----------------------------------------|
| Faizan Breached        | Search leaked data for emails, phone numbers, usernames , Id Pass And Govt Documents.                  | [Faizan Breached](https://t.me/FaizanBreach) |
| Leak Check Bot          | Check emails and usernames in leaked databases.                               | [Leak Check Bot](https://web.telegram.org/k/#@LeakCheckBot) |
| Sang Mata Bot           | Track username and name changes.                                              | [Sang Mata Bot](https://t.me/SangMata_beta_bot)   |
| Whois Bot               | Perform a simple domain WHOIS lookup.                                         | [Whois Bot](https://t.me/whois_bot)               |

---

## Custom Search Engines

| **CSE Name**          | **Link**                                                                                 |
|------------------------|-----------------------------------------------------------------------------------------|
| Commentgram CSE       | [Search Here](https://cse.google.com/cse?cx=006368593537057042503:ig4r3rz35qi#gsc.tab=0) |
| OSINT ME CSE          | [Search Here](https://cse.google.com/cse?cx=6c3e0c0d3da8e3b4a)                          |
| Telegago CSE          | [Search Here](https://cse.google.com/cse?q=+&cx=006368593537057042503:efxu7xprihg#gsc.tab=0) |

---

## Google Dorks

### **Telegram Group and Channel Dorks**

| **Dork**                              | **Use**                                                              |
|---------------------------------------|----------------------------------------------------------------------|
| `site:t.me "joinchat" "keyword"`      | Search for Telegram join links containing a specific keyword.        |
| `site:t.me "group" "keyword"`         | Locate Telegram groups using a specific keyword.                     |
| `site:t.me "channel" "keyword"`       | Search for Telegram channels related to a keyword.                   |
| `site:t.me "bot" "keyword"`           | Find Telegram bots related to a specific keyword.                    |
| `site:t.me "search" "keyword"`        | Search Telegram for groups and channels with a specific keyword.     |

---

### **Telegram Username and Profile Dorks**

| **Dork**                              | **Use**                                                              |
|---------------------------------------|----------------------------------------------------------------------|
| `site:telegram.me "@username"`        | Search for a specific Telegram username.                             |
| `site:t.me "@username"`               | Locate a Telegram username using the alternative domain.             |
| `site:t.me "keyword" intitle:"user"`  | Find usernames with a specific keyword in their title.               |
| `inurl:t.me "@username"`              | Search for Telegram URLs containing a specific username.             |
| `site:t.me "name:keyword"`            | Locate profiles with specific keywords in their names.               |

---

### **Telegram Leaked Data Dorks**

| **Dork**                              | **Use**                                                              |
|---------------------------------------|----------------------------------------------------------------------|
| `site:t.me "data leaks" "keyword"`    | Find Telegram links associated with leaked data and a keyword.       |
| `site:t.me "phone number" "keyword"`  | Search for phone numbers in Telegram links.                          |
| `site:t.me "email" "keyword"`         | Find Telegram links associated with leaked email data.               |
| `site:t.me "database" "keyword"`      | Locate Telegram links referencing databases with a keyword.          |
| `site:t.me "leaks" "keyword"`         | Search Telegram for links mentioning leaks with a specific keyword.  |

---

### **Telegram Bot Dorks**

| **Dork**                              | **Use**                                                              |
|---------------------------------------|----------------------------------------------------------------------|
| `site:t.me "bot" "keyword"`           | Search for Telegram bots related to a specific keyword.              |
| `site:telegram.me/bot "keyword"`      | Locate bots on Telegram using a specific keyword.                    |
| `site:t.me "Telegram Bot" "keyword"`  | Search for Telegram bots mentioning specific keywords.               |
| `site:t.me/bot "function"`            | Find bots offering specific functions (e.g., scraping, searching).   |

---

---

## YouTube Playlists

| **Channel Name**       | **Description**                                   | **Link**                                                                                |
|------------------------|---------------------------------------------------|----------------------------------------------------------------------------------------|
| Apple Guy              | Tutorials and guides on Telegram OSINT.          | [Apple Guy](https://www.youtube.com/watch?v=h2n-GN-4NJ4&list=PLqFbUIb5MftVSuZw0PTRuTWG33OxB8hkx) |
| Bemro                  | Comprehensive Telegram OSINT series.             | [Bemro](https://www.youtube.com/watch?v=8naENmP3rg4&list=PLa1uBOkthszRX38MxHuLDE5eX7IHlNj-N) |

---

## Videos

| **Video Name**         | **Description**                                              | **Link**                                                                 |
|------------------------|--------------------------------------------------------------|---------------------------------------------------------------------------|
| How to Obtain Telegram API | Step-by-step guide on obtaining a Telegram API.            | [Watch Here](https://www.google.com/search?q=how+to+obtain+a+telegram+api&tbm=vid) |
| Leveraging Telegram Bots | Automate country-specific OSINT workflows.                 | [Watch Here](https://www.youtube.com/watch?v=ruOZpW_QcVE)                |

---
## Contributing

Contributions are welcome! To contribute, fork the repository and submit a pull request with your improvements.

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Commit your changes (`git commit -am 'Add new feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Create a new Pull Request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact

For any questions or feedback, please contact [E-Mail Me](mailto:fk776794@gmail.com?subject=Feedback%20on%20Faizan%20Net&body=Hello%20Faizan,%0A%0AI%20have%20some%20feedback%20to%20share%20about%20your%20Faizan%20Net%20tool.%0A%0A%2D%20Issue%2FComplaint%3A%20[Please%20describe%20the%20issue%20or%20complaint]%0A%2D%20Suggestions%2FChanges%3A%20[Please%20provide%20your%20suggestions%20or%20changes]%0A%0AThank%20you!%0A%0ARegards,%0A[Your%20Name])

<!-- display the social media buttons in your README -->

[![instagram](https://github.com/shikhar1020jais1/Git-Social/blob/master/Icons/Instagram.png (Instagram))][2]
[![twitter](https://github.com/shikhar1020jais1/Git-Social/blob/master/Icons/Twitter.png (Twitter))][3]
[![linkedin](https://github.com/shikhar1020jais1/Git-Social/blob/master/Icons/LinkedIn.png (LinkedIn))][4]
[![github](https://github.com/shikhar1020jais1/Git-Social/blob/master/Icons/Github.png (Github))][5]

<!-- To Link your profile to the media buttons -->

[2]: https://www.instagram.com/EthicalFaizan
[3]: https://www.twitter.com/EthicalFaizan
[4]: https://www.linkedin.com/in/EthicalFaizan
[5]: https://www.github.com/faizan-khanx

## GITHUB STATS

![Faizan's GitHub stats](https://github-readme-stats.vercel.app/api?username=faizan-khanx&show=reviews,discussions_started,discussions_answered,prs_merged,prs_merged_percentage&theme=dark#gh-dark-mode-only)
