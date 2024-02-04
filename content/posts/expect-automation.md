---
title: Automating cli prompts with Expect
date: '2024-02-04T10:07:05Z'
tags: ["automation", "devops", "scripting"]
author: "Me"
draft: false
hidemeta: false
comments: true
description: "Using Expect to automate interative cli prompts"
disableShare: false
disableHLJS: false
hideSummary: false
cover:
    image: ""
    relative: false
    hidden: false
editPost:
    URL: "https://github.com/elliot-gould/elliot-gould.github.io/content"
    Text: "Suggest Changes"
    appendFilePath: true
---
Recently I was tasked with deploying a new application into AWS at my current role which used a script with *interative* prompts as it's only means of installing. It prompts for a url, you enter a url. It asks for an email, you enter an email etc...

There were no `--yes` or `--noninteractive` flags supported, or answer files I could use to answer these prompts in an automated way. This leaves the hacky option of trying to echo the answers into stdin using a bash script, for each prompt. To make matters worse, the prompts would actually change order and some would not be present at all depending on the information already in the database.

Struggling to think of a way to do this and many hours of googling later, I came across a across a tool called `expect`. A tool designed for exactly this, automating answers to interative cli prompts.
