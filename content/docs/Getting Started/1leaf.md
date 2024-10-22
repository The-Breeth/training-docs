---
title: Quick Start
type: docs
weight: 1
prev: docs/Getting Started
---

# Setting Up Your Development Environment

## Introduction

At **Breeth**, we prioritize having a well-configured development environment to ensure smooth workflows. In this guide, you will set up your environment to work with the **frontend** and **backend** branches of our training repository. You'll also install the necessary tools, configure your system, and generate SSH keys for GitHub access.

### Prerequisites

Before you begin, ensure you have the following tools installed:

1. **NVM (Node Version Manager)**: To easily manage Node.js versions.
2. **Git**: For version control.
3. **SSH Keys**: For secure access to GitHub.

---

### Step 1: Install Node.js Using NVM

Using **NVM** allows you to manage multiple versions of Node.js on the same machine, ensuring that you’re using the correct version for Breeth projects.

#### Installation Links

- **macOS/Linux**:
  Run the following command in your terminal:

  ```bash
  curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
  ```

  After installation, load `nvm` into your shell:

  ```bash
  export NVM_DIR="$HOME/.nvm"
  [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
  ```

- **Windows**:
  Download the NVM installer from the [nvm-windows GitHub repository](https://github.com/coreybutler/nvm-windows/releases). Follow the installation instructions.

#### Installing Node.js with NVM

Once **NVM** is installed, install the recommended Node.js version (LTS) using:

```bash
nvm install --lts
```

Verify the installation with:

```bash
node -v
```

---

### Step 2: Install Git

- **macOS**:
  You can install Git via Homebrew:
  ```bash
  brew install git
  ```
- **Windows**:
  Download the installer from the [official website](https://git-scm.com/).
- **Linux**:
  Install Git via your package manager:
  ```bash
  sudo apt install git
  ```

Verify the installation by running:

```bash
git --version
```

---

### Step 3: Generate and Add SSH Keys for GitHub

#### 1. Generate a New SSH Key

Open your terminal and run:

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

When prompted, you can save the key in the default location. Then, add the SSH key to your SSH agent:

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

#### 2. Add SSH Key to GitHub

Copy the SSH key to your clipboard:

```bash
cat ~/.ssh/id_ed25519.pub
```

Go to your [GitHub SSH settings](https://github.com/settings/keys) and click **New SSH Key**. Paste your key and save it.

---

### Step 4: Clone the Training Repository

Our training repository is organized into two branches: **frontend** and **backend**. You can choose the one you want to focus on, or switch between them as needed.

1. **Clone the repository**:

   ```bash
   git clone git@github.com:The-Breeth/training.git
   ```

2. **Switch branches**:
   - For frontend training, use:
     ```bash
     git checkout frontend
     ```
   - For backend training, use:
     ```bash
     git checkout backend
     ```

---

### Step 5: Install Dependencies

After cloning the repository and switching to your desired branch, install the project dependencies:

```bash
npm install
```

---

### Step 6: Running the Development Server

You can now start the development server:

```bash
npm run dev
```

Open your browser and navigate to `http://localhost:5173` to view the running application.

---

### Conclusion

By following these steps, you have successfully set up your development environment. You are now ready to start working on either the **frontend** or **backend** of the project. In the next section, we will explore the project structure and important components to help you navigate the codebase.

### You can choose which side you wanna pick

{{< cards >}}
{{< card link="/docs/front-end" title="Front End" icon="desktop-computer" >}}
{{< card link="/docs/back-end" title="Back End" icon="server" >}}
{{< /cards >}}
