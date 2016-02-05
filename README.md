# fa_notifier

This runs [a script to scrape FurAffinity and send PushBullet notifications](https://gist.github.com/Treeki/006a30d2f6e07213aa51).

*   Use at your own risk.
*   I did not write the script.
*   Seriously, don't ask me for help with it.

## Usage

### Create a data container

    docker create --name fa_notifier-data --volume /data tianon/true

### Set up the config file in the data container

    docker run --tty --interactive --rm --volumes-from fa_notifier-data koinu/fa_notifier sh

    $ cp /app/config.example.json ./config.json
    $ vi config.json

### Run the app

    docker run --rm --volumes-from fa_notifier-data koinu/fa_notifier
