# GitHub-SSH-solution
Git's SSH Permission Denied (PublicKey) Error on GitHub


Troubleshooting Git SSH Permission Denied
1. Common Culprit: Wrong Username
The most frequent mistake is using your personal GitHub username in the SSH address.

Incorrect: cameronmc@github.com 

Correct: git@github.com 

GitHub uses the git user for all SSH connections and identifies you specifically based on your unique SSH keys.

2. Verifying Local SSH Keys
If using the correct username doesn't work, ensure you have the necessary key files in your local .ssh directory.

Location: Typically found in your user home directory (e.g., C:\Users\Owner\.ssh on Windows or ~/.ssh on Linux/macOS) 

Required Files: You must see both a private key (e.g., id_rsa) and a public key (e.g., id_rsa.pub) 

3. Generating New SSH Keys
If your current keys aren't working, it is often easiest to delete the old ones and generate a fresh pair 

Open Terminal/PowerShell and run:
ssh-keygen -o -t rsa -C "your-email@example.com"

2.  **Save the file** to the default `.ssh` folder and skip the passphrase by pressing **Enter** [02:54](http://www.youtube.com/watch?v=Irj-2tmV0JM&t=174).
3.  **Copy the Public Key:** Open the `.pub` file and copy its entire text content [03:45](http://www.youtube.com/watch?v=Irj-2tmV0JM&t=225).


4. Registering the Key on GitHub**
For the connection to work, your **public key** must be registered in your GitHub account settings.

  a.  Log in to [GitHub](http://www.github.com) and go to **Settings** > **SSH and GPG keys** [03:59](http://www.youtube.com/watch?v=Irj-2tmV0JM&t=239).
  b.  Click **New SSH Key**.

3.  Paste your public key into the box, give it a descriptive title (e.g., "My Laptop"), and save [04:10](http://www.youtube.com/watch?v=Irj-2tmV0JM&t=250).


5. Testing the Connection**
Once the keys are in sync, you can verify the connection without cloning a full repository by running:
{bash}
ssh -T git@github.com
