# How to use KaguraMea

## Before:

### Linux:

#### Local test:
- Clone all files to the local, and run the `make` command in the Print, Read, Server folder
- Empty the `userdata` file in the Server folder
- Run `Server`, `Read`, `Print` in sequence, and enter all instructions at `Read`

#### Network operation:
- Clone all the files in the Server folder to your server, and run the `make` command in this folder
- Clone all files in the two folders Print and Read to the local
- Insert 127 of Read_Manager.cpp `serv_addr.sin_addr.s_addr = inet_addr ("127.0.0.1");` Change the IP address (127.0.0.1) to the address of your server in the statement, and run the `make` command in the Print and Read folders
- Empty the `userdata` file in the Server folder
- Run `Server`, `Read`, `Print` in sequence, and enter all instructions at `Read`

---

## When using it
- Read it
- Or check all supported operations [here](https://github.com/XDeviation/KaguraMea-ACommonIM/wiki)

## Help documentation

### Before landing
- Enter `1` to register a new user
- You need to enter the user name and password in order on the new user registration interface. The user name must be within 6-100, and the password must be within 6-20. After that, you will get a friend key that is the same as the existing user name. You can add friends by searching for the friend key of others.
- Enter `2` to log in to an existing account
- You need to enter the user name and password in order on the login interface, the server will automatically determine whether the user exists and the password is correct.

### After landing
- Joining the chat will pull historical messages to the local.
- Enter `5` to change the password
- There is no secondary verification function for changing the password. If you make a mistake, please go to the corresponding folder in `./Server/usrdata` to reset it.

### Troubleshooting

#### Port conflict
- Put the statement on line 128 of Read_Manager.cpp
`serv_addr.sin_port = htons (19198);`
The port in (19198) is changed to an idle port

- Or put line 144 of Read_Manager.cpp
`my_addr.sin_port = htons (10086); and line 16 of Print_Manager.cpp
`serv_addr.sin_port = htons (10086);`
The port in (10086) is changed to an idle port