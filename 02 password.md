Router(config)#enable password password
##configures a password to protect privileged exec mode

Router(config)#service password-encryption
##encrypts the enable password (and other passwords)

Router(config)#enable secret password
##configures a more secure, always-encrypted enable password

Router(config)#run privileged-exec-level-command
##executes a privileged-exec level command from global configuration mode

Router(config)#no command
##removes the command
