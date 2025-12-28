---
title: Hello World
---
Today I spent several hours trying to set up Quartz on this site. I'm really excited to start using this setup though! I ran into issues and so here is a bit of documentation about what I did, mostly as fill content while I figure out how I'm going to be using the Digital Garden.

Problem: My Quartz build is generating files with a double extension: filename.md.html instead of the expected filename.html. This causes 404 errors on a standard static host because the server looks for filename or filename.html and finds nothing.

Workaround: I have modified my package.json build command to manually "fix" the output after Quartz finishes:

Rename: It finds all .md.html files in public/ and renames them to.html.

Rewriting: It runs a sed command across all emitted files (HTML and JSON) to change internal strings of .md.html or .md to .html.

With my current workaround I MUST put .md at the end of my files in Obsidian or they will 404. 

Current Configuration:

Config: enableSPA: false, prettyLinks: true.

Environment Variables: CLEAN_URLS: true.

Windows 10 LTSC IoT
Quartz 4.5.2
Obsidian 1.10.6 
npm 11.6.2
node 24.12.0
Host: DigitalOcean App Platform (Static Site)
Public Github:![[]]
https://github.com/pipeargill/pipeargill.com