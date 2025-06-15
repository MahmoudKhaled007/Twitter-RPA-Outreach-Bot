# Twitter RPA Outreach Bot

This repository contains a UiPath automation project that performs outreach actions (Likes,Comments, Messages, or Both) on Twitter/X to help freelancers and consultants connect with potential clients. The automation is driven by Grook AI for personalization and is fully configurable via Excel files.

---

## 📌 Features

- ✅ Takes input from an Excel sheet with target profile links  
- ✅ Uses a config Excel file to define prompts and automation settings  
- ✅ Offers a UI window for selecting desired action: Comment, Message, or Both  
- ✅ Checks each Twitter profile for required elements (posts, message button, follow button, Grook availability)  
- ✅ Generates personalized content via Grook:
  - Likes & analyzes recent posts
  - Summarizes user profile
  - Generates tailored comments or messages
- ✅ Skips users already messaged
- ✅ Saves all actions in an output Excel log
- ✅ Automatically rotates between multiple Chrome user profiles after reaching Grook limits
- ✅ Circular profile rotation (Profile A → Profile B → Profile A...)
- ✅ Error handling:
  - Screenshots on error
  - Logs error in Excel
  - Skips problematic profile
- 🚧 **Planned Feature:** Proxy rotation for enhanced anonymity and anti-bot detection

---

## 🤖 DEMO
You can watch a Demo from here [DEMO](https://youtu.be/Aa2esaM9Qb0).

---
## 📥 Input Files

### 1. `target_accounts.xlsx`
- Contains list of target Twitter profile URLs.

### 2. `ChromeProfiles.xlsx`
- Contains list of chrome profiles to rotate on.

### 3. `input_prompts.xlsx`
- Contains list prompts to use, make it easy to edit.


## 🧠 How It Works

### Step-by-step Workflow

1. **Read Input Excel**: Target profiles  
2. **User Action Selection**: Comment / Message / Both  
3. **Loop Over Profiles**  
   - Validate interactivity (check for posts, message, follow, Grook)
   - **If Comment Selected**:
     - Like latest post
     - Analyze post with Grook
     - Generate a comment prompt (e.g., “Check your DM”)
     - Post comment
   - **If Message Selected**:
     - Summarize profile with Grook
     - Generate personalized message prompt
     - Check message history
     - If new → Send message
   - **If Both Selected**:
     - Perform both actions above  
4. **Rotate Chrome Profile** upon Grook rate limit  
5. **Log Actions**: Append data to `OutputLog.xlsx`  
6. **Error Handling**:
   - Capture screenshot
   - Log error in Excel
   - Skip profile

---

## 🔁 Rotation Logic

- Chrome Profiles rotate in circular order  
- Switch on Grook rate-limit or account restrictions  
- Rotation continues until all profiles are processed  

---

## ✅ Output Log (`OutputLog.xlsx`)

Logs the following for each profile:

- Profile URL  
- Commented: Yes/No  
- Messaged: Yes/No  
- Chrome Profile Used
- Personalized Message
- Personalized Comment
- Timestamp  
- Error (if any)  

---

## 🚀 Requirements

- UiPath Studio (tested with 2023.x or newer)  
- UiPath Excel, UIAutomation, System & WebAutomation packages  
- Grook API Access / Installed Extension  
- Multiple Chrome user profiles pre-configured  
- Set Shortcut to Activate CTRL+ Y Chrome Extention [Screenshot & Screen Recorder Tool]9https://chromewebstore.google.com/detail/ijejnggjjphlenbhmjhhgcdpehhacaal?utm_source=item-share-cb)
---

## 📅 TODO

- Add Proxy support & rotation  

---

## 🤝 Contributing

Want to improve the automation or UI? PRs are welcome. Create an issue or pull request.

---

## 📜 License
This project is licensed under the **Apache 2.0 License**. See [LICENSE](LICENSE) for details.

## 📧 Contact

For freelance projects or RPA consulting:  
**Mahmoud Khaled**  
Freelance UiPath | Power Automate | Python  
Email: **Mahmoud.khkamal@gmail.com**
