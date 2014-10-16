![Pigshell](images/pigshell-logo.png "Pigshell")

## Pigshell - Unix the web

[Pigshell] (http://pigshell.com/) is a pure client-side Javascript app running in the browser, which presents resources on the web as files. These include public web pages as well as private data in Google Drive, Dropbox, Facebook and even your desktop. It provides a command line interface to construct pipelines of simple commands to transform, display and copy data.

Pigshell is free software, released under the GNU GPLv3.

Pigshell is inspired by Unix philosophy: Everything is a file. Programs should do one thing well. Create tools by stringing together a combination of simpler tools. Like human language, CLIs give us freedom of expression - we can generate infinite meaningful combinations from a limited number of words to effectively deal with the combinatorial explosion of variety thrown up by the modern web environment.

We're far from done, but here are some of the things you can do right now:
Backup Google Drive to your desktop: 

### Installation
Simply visit [http://pigshell.com] (http://pigshell.com) and type away. Modern (~early 2014) versions of Chrome, Firefox and Safari should work fine on all desktop platforms. Mobile browsers, Internet Explorer and others are not supported at the moment.

Running the `psty` server on your desktop is strongly recommended. It exposes a local directory for pigshell to use as a `/home`, serves as a proxy HTTP server, and lets pigshell pipe web data through desktop Unix utilities. Psty works only on Unix currently.

#### Psty
`Psty` is a little server you run on your desktop as a sidekick to Pigshell. While pigshell can be used standalone, `psty` (the p is silent, as in Psmith) adds so much to its power and reach as to be practically indispensable.

`Psty` implements three services:

1. **Local file server:** `Psty` exposes a local directory of your choice to pigshell, letting you read and write files stored on your desktop from pigshell.
2. **HTTP proxy server:** `Psty` proxies HTTP requests for pigshell, giving it access to any URL on the web, bypassing the same-origin restrictions faced by Javascript apps in the browser.
3. **Websocket server:** Every unix app on the desktop which uses stdin/stdout can participate in a pigshell pipeline.
Together, these features enable powerful data movement and transformation pipelines. 

`Psty` installation:

    $ wget -O ~/bin "http://pigshell.com/v/0.6.2/psty.py"
    $ chmod 755 ~/bin/psty.py
    $ mkdir -p ~/psty
    $ echo alias psty='~/bin/psty.py -a -d ~/psty' >> ˜/.bashrc
    $ cd ~
    $ . .bashrc
    
`Psty` starting: 

    $ psty&