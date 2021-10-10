## Generating ssh key

- `ssh-keygen -t ed25519 -C "your_email@example.com"`
- Follow instructions

## Start ssh agent in background

- `eval "$(ssh-agent -s)"`

## Add identity 

- `ssh-add ~/.ssh/id_ed25519`

## Add ssh key to github
- `cat ~/.ssh/id_ed25519.pub`
