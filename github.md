# Config username and email

- `git config --global user.name "your_github_username" `
- `git config --global user.email "your_github_email"`
- `git config -l`

# Cache configrations

- `git config --global credential.helper store`

# Remove Cache

- `git config --global --unset credential.helper `
- `git config --system --unset credential.helper`

## Generating ssh key

- `ssh-keygen -t ed25519 -C "your_email@example.com"`
- Follow instructions

## Start ssh agent in background

- `eval "$(ssh-agent -s)"`

## Add identity 

- `ssh-add ~/.ssh/id_ed25519`

## Add ssh key to github
- `cat ~/.ssh/id_ed25519.pub`
