# AmsterdamPHP - Meetup.com Raffler

This application enables us to raffle off stuff to our meetup attendees. It uses the Meetup.com API to get all check ins, and then uses the Random.org API to randomly select winners.

## Installation

### Install into a virtual machine. (Linux and OSX users only)

1. `git clone git@github.com:AmsterdamPHP/meetup-raffle-machine.git --recursive`
2. Ensure that Virtualbox, Vagrant, and Ansible are installed.
3. run `vagrant up`
4. create config/parameters.yml (get your API key from [meetup.com](https://secure.meetup.com/meetup_api/key/))

    ```
    meetup_group:   amsterdamphp
    meetup_api_key: YOUR_MEETUP_API_KEY
    ```

5. (from within the machine) `composer install`
6. (from within the machine) `compass compile`

### Install directly onto your host machine.

1. Get code
2. Give permissions

    ```
    sudo chmod -Rf +a "`whoami` allow delete,write,append,file_inherit,directory_inherit" cache logs
    sudo chmod -Rf +a "<apache user> allow delete,write,append,file_inherit,directory_inherit" cache logs
    ```

3. Install Dependencies

    ```
    gem update --system
    gem install compass
    gem install susy
    ```

4. Compile stylesheets

    ```
    compass compile
    ```

5. Create config/parameters.yml

    ```
    meetup_group:   amsterdamphp
    meetup_api_key: YOUR_MEETUP_API_KEY
    ```

## How to use it

1. Open the app index page to be presented with a list of meetups.
2. Click on a meetup.
3. Press [space] or [page down] to start raffles.

The page down key allows us to use most presentation remotes as well.
