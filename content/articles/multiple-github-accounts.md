---
Title: Managing multiple account on GitHub
Date: 03 Dec 2024
Summary: What are the options now, theirs benefits and best solution
draft: true
---

If you have multiple GitHub account it could be changeling to switch between them every time you need so. During my programming experience I had several approaches to it. What options I have used:

## 1. Deleting credentials

You open Windows “Credential manager” and delete your local GitHub login and password. Then you login again with account you need.
But you need to change your git config in the terminal to:

```js
git config --global user.name "GITHUB_USERNAME"
git config --global user.email "MY_NAME@example.com"
```

Main disadvantage is if you forget to do it, then the other account could appear as contributor. To remove it you need to create new repo.

## 2. Creating several Windows profiles

This approach would guarantee that every GitHub account is connected to each own VS Code account.
Significant disadvantage is that it takes time to switch between them. Specially, if you need to check how you written code from the other account in private repo.

## 3.SSH keys

I haven’t tried it myself, but seen YouTube videos and it was confusing - the process of connecting it.

## 4.GitKraken
This application works very well and changing between account is pretty fast. Best for big projects on my opinion, because it’s designed to efficient managing of GitHub branches.

## 5.GitHub Codespace
This option is what I have chosen. I’m not working on big projects and programming is just a hobby. To switch account, simply enter your another GitHub profile via browser and then VS Code.
But there is several limitations with it. First is that you are limited with usage time. It’s just 120 hours in 28 days and your open codespaces storage limited to 15 GB.
Biggest advantage is it’s comparability. It can be opened via VS Code and you connect directly to GitHub server.

To sum it all up, as you would guess, what you choose depends on what you need.