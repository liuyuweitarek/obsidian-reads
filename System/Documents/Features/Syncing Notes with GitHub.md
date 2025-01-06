# Syncing Notes with GitHub

You can push your notes to GitHub for backup or syncing across multiple devices. However, note that Git does not handle conflicts automatically; you will need to resolve them manually. For guidance, refer to this [merge conflict resolution tutorial](https://youtu.be/DloR0BOGNU0?si=cLr7QNoX59U8_kz1).
## Usage

- **Stage and Commit Changes:**  
    Shortcut: `Ctrl + +`.
    
- **Push Changes:**  
    Shortcut: `Ctrl + ↑`.
## Setup

1. **Install [Git](https://git-scm.com/downloads) on your machine.**

2. **Create a GitHub Account:**
	
	If needed, create an account using this [tutorial](https://youtu.be/Gn3w1UvTx0A?si=oL6Q2g6muDJqpH5U).

3. . **Create a GitHub Repository:**  
	
	Open a private repository using the [Obsidian Reads template](https://github.com/liuyuweitarek/obsidian-reads). Click **"Use this template"**.

4. **Clone the Repository Locally:**
		
	Run the following command in your terminal:
	```
	$ git clone https://github.com/{YOUR-GITHUB-USERNMAE}/obsidian-reads.git
	```
	
5. **Set Up the Vault in Obsidian:**
	
	Open the cloned folder in Obsidian and click **"Trust Author of this Vault"**.

6. **Configure the Git Plugin in Obsidian:**
	
	- Navigate to **Settings** > **Community Plugins** > **Git**.
	- Enter your GitHub username and email in the plugin's configuration panel.
		<img src="../assets/plugin-git-config.JPG" width="500" height="500"/>
1. **Push Changes with Personal Access Token (First Time Only):**
    
    - Generate a **Personal Access Token** on GitHub:  
        Go to **Settings** > **Developer Settings** > **Personal Access Tokens (classic)** > **Generate New Token**.
    - Use this token to authenticate during your first `git push`. **Keep the token secure and private.**
		![](../assets/plugin-git-first-login-personaltoken-githubpage.JPG)
		![](../assets/plugin-git-first-login-personaltoken.JPG)
		![](../assets/plugin-git-first-login-auth.JPG)
1. **Daily Workflow:**
    
    - Use `Ctrl + +` to stage and commit changes.
		![](../assets/plugin-git-commit-success.JPG)
    - Use `Ctrl + ↑` to push changes to GitHub.