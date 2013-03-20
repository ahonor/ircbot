# Option Answers

- gh-pages repo         = git@github.com:ahonor/irclog-ghpages.git
- posts directory       = $CWD/irclog/_posts
- IRC server (optional) = irc.freenode.net
- IRC channel           = rundeck
- IRC nick (optional)   = ircbot

# Start
rerun irclog:start --channel rundeck --nick irclog$$ --dir ./irclog --repo $REPO


## Checkout the gh-pages site

rerun irclog:checkout --repo git@github.com:ahonor/irclog-ghpages.git --dir ./irclog

    [[ "${REPO}" =~ .*/(.*).git ]] || rerun_die "Failed parsing repo name"
    git clone $REPO
    cd ${BASH_REMATCH[1]}

## Connect to IRC channel and digest messages

    (rerun irclog:connect -channel rundeck --nick irclog$$       |
    rerun irclog:digest --format ghpost --dir ./irclog/_posts ) &
    connect_pid=$!
    
## Check for changes and commit the posts

    rerun irclog:push --dir ./irclog
   


