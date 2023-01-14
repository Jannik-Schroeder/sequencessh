# sequencessh

sqssh is a command line tool for connecting to multiple servers simultaneously. It reads a list of servers from a configuration file and allows you to execute commands on all of them at once.

## Usage

```
sqssh [LIST] [COMMAND]
```

+ `'LIST'` is the name of the server list to connect to. This list must be defined in the configuration file located in `'~/.config/sqssh/config'`.

+ `'COMMAND'` is the command to be executed on all servers in the list.

## Configuration
The first time you run sqssh, it will check if the configuration file exists in `'~/.config/sqssh/config'`. If it doesn't, it will prompt you to create one. The configuration file is used to define the server lists that sqssh can connect to.

Each server list must be defined on a new line, starting with a `'-'` followed by the list name. For example:

```
- listname1
- listname2
```
  You also need to create a file for every server list in the same directory with the name of the list and write down the server in the format:

```
- user@server1
- user@server2
```
## Example
To connect to a server list named `'example'` and execute the command `'ls -la'`, you would use the following command:

```
sqssh example "ls -la"
```
This would execute the command on all servers in the list, and display the output for each one.

# Help
You can display the help message by running:

```
sqssh --help
```
or

```
sqssh -h
```
## Note
The script is using StrictHostKeyChecking=no flag while connecting through ssh, which could lead to security vulnerability.
It's recommended to check the ssh-keys of the server before connecting to it.





