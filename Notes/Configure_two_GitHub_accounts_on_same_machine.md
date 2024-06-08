To configure two GitHub accounts using ED25519 encryption on the same machine, you need to generate separate SSH keys for each account, add them to the SSH agent, and configure the SSH configuration file accordingly. Here are the steps:

### Step 1: Generate SSH Keys

1. **Generate an SSH key for the first account (noumanshah436):**
   ```sh
   ssh-keygen -t ed25519 -C "noumanshah436@gmail.com"
   ```
   Save the key as `~/.ssh/id_ed25519_noumanshah436`.

2. **Generate an SSH key for the second account (noumanrehman042):**
   ```sh
   ssh-keygen -t ed25519 -C "nouman.rehman@devsinc.com"
   ```
   Save the key as `~/.ssh/id_ed25519_noumanrehman042`.

### Step 2: Add SSH Keys to the SSH Agent

1. **Start the SSH agent:**
   ```sh
   eval "$(ssh-agent -s)"
   ```

2. **Add the SSH keys to the agent:**
   ```sh
   ssh-add ~/.ssh/id_ed25519_noumanshah436
   ssh-add ~/.ssh/id_ed25519_noumanrehman042
   ```

### Step 3: Add SSH Keys to GitHub Accounts

1. **Copy the contents of the public keys:**
   ```sh
   cat ~/.ssh/id_ed25519_noumanshah436.pub
   cat ~/.ssh/id_ed25519_noumanrehman042.pub
   ```

2. **Go to GitHub, sign in to each account, and add the SSH keys:**

   - For `noumanshah436`, go to **Settings > SSH and GPG keys**, and add the key from `id_ed25519_noumanshah436.pub`.
   - For `noumanrehman042`, go to **Settings > SSH and GPG keys**, and add the key from `id_ed25519_noumanrehman042.pub`.

### Step 4: Configure SSH Config File

1. **Open or create the `~/.ssh/config` file:**
   ```sh
   nano ~/.ssh/config
   ```

2. **Add the following configuration:**
   ```plaintext
   # GitHub account for noumanshah436
   Host github-noumanshah436
       HostName github.com
       User git
       IdentityFile ~/.ssh/id_ed25519_noumanshah436

   # GitHub account for noumanrehman042
   Host github-noumanrehman042
       HostName github.com
       User git
       IdentityFile ~/.ssh/id_ed25519_noumanrehman042
   ```

### Step 5: Clone Repositories Using the Correct Host

1. **For the first account (noumanshah436):**
   - To clone repository(https://github.com/noumanshah436/programming-toolkit.git), <br> run the following command
   `git clone git@github-noumanshah436:noumanshah436/programming-toolkit.git`

   ```sh
   git clone git@github-noumanshah436:username/repository.git
   ```

2. **For the second account (noumanrehman042):**
   ```sh
   git clone git@github-noumanrehman042:username/repository.git
   ```

### Step 6: Set Up Git Configuration for Each Repository

1. **Navigate to each repository and set the corresponding user details:**

   For `noumanshah436`:
   ```sh
   cd /path/to/first/repository
   git config user.name "noumanshah436"
   git config user.email "noumanshah436@gmail.com"
   ```

   For `noumanrehman042`:
   ```sh
   cd /path/to/second/repository
   git config user.name "noumanrehman042"
   git config user.email "nouman.rehman@devsinc.com"
   ```

### Final Configuration

The `~/.ssh/config` file should look like this:
```plaintext
# GitHub account for noumanshah436
Host github-noumanshah436
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519_noumanshah436

# GitHub account for noumanrehman042
Host github-noumanrehman042
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519_noumanrehman042
```

By following these steps, you will have configured your system to use two GitHub accounts with separate SSH keys, allowing you to work seamlessly with both accounts on the same machine.