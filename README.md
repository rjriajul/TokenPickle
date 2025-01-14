# Generate Token Pickle on Android (Google OAuth 2.0 Update)

Follow these steps to generate the `token.pickle` file on Android using Termux.

---

## Steps

### 1. Install Termux  
Download and install [Termux](https://github.com/termux/termux-app/releases).  

### 2. Set Up Termux  
Open Termux and run this command to update, install necessary packages, and set up Python:

```bash
apt update && apt upgrade -y && apt install git python3 python3-pip -y && python3 -m pip install --upgrade pip && pip install google-api-python-client google-auth-httplib2 google-auth-oauthlib
```

### 3. Clone the Repository  
Run the following to clone the `TokenPickle` repository:

```bash
git clone https://github.com/RjRiajul/TokenPickle
```

### 4. Add `credentials.json`  
Move the `credentials.json` file to your phone’s internal storage (not an SD card). Then, give Termux storage access:

```bash
termux-setup-storage
```

Copy the file into the project folder:

```bash
cd sdcard
cp credentials.json /data/data/com.termux/files/home/TokenPickle
```

### 5. Generate the Token  
Navigate to the project folder and run the script:

```bash
cd TokenPickle
python3 generate_token.py
```

Copy the URL displayed, open it in a browser, and log in to your Google account. After successful authentication, you’ll see the message:  
**“The authentication flow has completed. You may close this window.”**

### 6. Save `token.pickle`  
Copy the generated token to your phone's storage:

```bash
cp token.pickle /sdcard
```

---

## Done! 🎉  
You’ll find `token.pickle` in your phone’s internal storage.  


## Credit

[`SilentDemonSD`](https://github.com/SilentDemonSD)
