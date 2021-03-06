---
template: post
title: 'Save username and password in GIT'
featuredImage: '../featuredImages/git.png'
date: '2019-11-13'
author: 'Pabon'
profileUrl: 'https://github.com/shahnawaz-pabon'
category: 
    - Git
tags:
    - git
    - git-config
---

### Run

<div class=fakeMenu>
  <div class="fakeButtons fakeClose"></div>
  <div class="fakeButtons fakeMinimize"></div>
  <div class="fakeButtons fakeZoom"></div>
</div>

```bash
$ git config --global credential.helper store
```

After running this command, when you **push** to your repository or **pull** from your repository, you'll get asked `username` and `password` for first time.
Then credentials will be stored into your home directory named `.git-credentials` file in plaintext.
<br/>

You can use this command to store your credentials into cache memory for specific time(in seconds).

<div class=fakeMenu>
  <div class="fakeButtons fakeClose"></div>
  <div class="fakeButtons fakeMinimize"></div>
  <div class="fakeButtons fakeZoom"></div>
</div>

```bash
$ git config --global credential.helper 'cache --timeout=14400'
```
This command will remember your credentials for 4 hours. Your `username` and `password` will be asked for the first time during **push** or **pull** as well.
<br/>

These commands will store your `username, password and email` in `.gitconfig` file into your home directory.

<div class=fakeMenu>
  <div class="fakeButtons fakeClose"></div>
  <div class="fakeButtons fakeMinimize"></div>
  <div class="fakeButtons fakeZoom"></div>
</div>

```bash
$ git config --global user.name "your username"
$ git config --global user.password "your password"
$ git config --global user.email "your email"
```

**Storing global email would help you to [count](https://help.github.com/en/github/setting-up-and-managing-your-github-profile/why-are-my-contributions-not-showing-up-on-my-profile#contributions-that-are-counted) your github contribution during commits.**
