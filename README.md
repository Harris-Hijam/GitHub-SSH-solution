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
