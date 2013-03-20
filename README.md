# Option Answers

- gh-pages repo         = git@github.com:ahonor/irclog-ghpages.git
- posts directory       = $CWD/irclog/_posts
- IRC server (optional) = irc.freenode.net
- IRC channel           = rundeck
- IRC nick (optional)   = ircbot

# Start the logging bot.
rerun irclog:start --channel rundeck --nick irclog$$ --dir ./irclog --repo $REPO


## Check its status

rerun irclog:status --dir ./irclog

## Connect to IRC channel and digest messages

    rerun irclog:connect -channel rundeck --nick irclog$$       |
    rerun irclog:digest --format ghpost --dir ./irclog/_posts  &

    
## Check for changes and commit the posts

    rerun irclog:push --dir ./irclog
   


