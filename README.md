# Demo CTF for SBSEG2017

Welcome to the demonstration CTF for SBSEG2017.

## Registration
1. All team members must have a GitHub account and [configure a SSH key in their account settings](https://github.com/settings/keys).

2. All team members must have the git client [correctly set up](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup). If you have never used git before, run:
   ```bash
   git config --global user.name "John Doe"
   git config --global user.email johndoe@example.com
   ```

3. All team members must clone the repository and install the dependencies:
   ```bash
   git clone git@github.com:pwn2winctf/sbseg2017.git
   cd 2017
   sudo apt-get install libsodium18
   curl https://bootstrap.pypa.io/get-pip.py | sudo -H python
   sudo -H python -m pip install -r pip-requirements.txt
   ```
   **Notes**: 
   
	If you are using Ubuntu 14.04, add [ppa:elt/libsodium](https://launchpad.net/~elt/+archive/ubuntu/libsodium) to your system to be able to install `libsodium18`.

	If you are using Mac OS, install libsodium with `brew install libsodium`.

4. If dependencies are installed correctly, you should now see the help menu when calling:
   ```bash
   ./ctf -h
   ```

5. The **leader of the team** must execute the following command and follow the instructions to register the team:
   ```bash
   ./ctf init
   ```

6. After that, **the leader** must share the `team-secrets.json` with the members of the team. The **other members of the team** must place the `team-secrets.json` file shared by the leader in their `2017` directory.

7. The **other members of the team** must login to GitHub without registering a new team, by running:
   ```bash
   ./ctf login
   ```
   If you are using OTP, you will need to login using a [token] with public_repo scope (https://github.com/settings/tokens) running:
   ```bash
   ./ctf login --token [TOKEN]
   ```

## Challenges

Challenges will be available at https://game.pwn2win.party/sbseg2017.

If you prefer to browse them locally, you may also run a local webserver by typing `./ctf serve`, or list challenges through the command line interface:
```bash
./ctf challs
```

## Flag submission

To submit a flag:
```bash
./ctf submit --chall chall-id 'CTF-BR{flag123}'
```

You may omit `--chall chall-id` from the command, however it will be slower to run this way. In this case, we will look for the flag in every challenge released until now.

## Scoreboard

You can see the scoreboard in the game link (https://game.pwn2win.party/sbseg2017), locally (if you ran the local webserver) or through the command line interface:
```bash
./ctf score --names --pull
```

## Support

You may reach us through #tecland at irc.freenode.net.
