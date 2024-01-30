# Generating SSH Keys for GitHub

### Configure Git User Details
- Set up Git configuration on your machine by providing your GitHub user information. 
- Open the Terminal and execute the following commands, replacing "user_name" and "your_email@gmail.com" with your GitHub username and email:

  ```nginx
  git config --global user.name "user_name"
  ```
  
  ```nginx
  git config --global user.email "your_email@gmail.com"
  ```

- Optional: Set default branch name for `git init`

  ```nginx
  git config --global init.defaultBranch main
  ```
  
- To confirm the configured details:
  
  ```nginx
  git config --global --list
  ```

### Generate SSH Keys

- Open the Terminal and run the following command, replacing "your_email@example.com" with your GitHub email address.
- If your system supports Ed25519, use the first command; otherwise, use the second command for legacy systems like older computer systems or environments that may not support newer cryptographic algorithms like Ed25519:

  **For Ed25519 algorithm:**
  ```nginx
  ssh-keygen -t ed25519 -C "your_email@example.com"
  ```
  
  **For RSA algorithm (legacy systems):**
  ```nginx
  ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
  ```

- During the process, you'll be prompted to specify a file to save the key. Press Enter to use the default location. 
- At the passphrase prompt, enter a secure passphrase or press Enter for no password. 
- Repeat the passphrase if entered. 
- This generates a new SSH key, using the provided email as a label.

### Add SSH Key to GitHub

- Retrieve the SSH public key:
  ```nginx
  cat ~/.ssh/id_ed25519.pub
  ```
- Copy the entire public SSH key.

### In your GitHub account, 
- Navigate to Settings > SSH and GPG keys > Select "New SSH key" > Provide a title and paste your SSH key.

**Your SSH key is now configured for GitHub.**
