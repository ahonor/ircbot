
## Start the logging bot.

    rerun irclog:start --channel my_channel --nick irclog$$ --dir ./irclog --repo git@github.com:ahonor/irclog-ghpages.git


## Check its status

    rerun irclog:status --dir ./irclog

## Stop the logging bot

    rerun irclog:stop --dir ./irclog

## Connect to IRC channel and digest messages

    rerun irclog:connect -channel my_channel --nick irclog$$       |
    rerun irclog:digest --format ghpost --dir ./irclog/_posts  &

    
## Check for changes and commit the posts

    rerun irclog:push --dir ./irclog
   


