In KOReader the _SSH server_ settings are under Network in the _tools menu_ (Cog icon).

The ssh server is dropbear. Openssh's sftp server is also installed.
The `authorized_keys` file is at `settings/SSH/authorized_keys`.
Username is root.
`Login without password` lets you log in with any password (it's not to do with keys).


# Connecting through SFTP - without password

You can connect to device when it is online (in your home WiFi network) with SFTP if you setup your SSH to allow root logins without password.

First setup SSH to allow connecting without password in SSH menu (which is WiFi menu):

![](https://user-images.githubusercontent.com/202757/62869299-de1f4700-bd17-11e9-946c-1940853e1069.png)

After that setup any standard FTP client to connect using the device's specific IP address (this is shown when starting the SSH server and also available under network info), and using port `2222` (standard FTP port is 22). Like shown on image below (leave password field empty):

![](https://user-images.githubusercontent.com/202757/62867437-8a126380-bd13-11e9-8d08-4ebd5f25dcf8.png)

After that you can transfer your files to and from your device with FTP client.

# Troubleshooting

## ssh fails with error message `packet_write_wait: Connection to ... port 2222: Broken pipe
Try disabling TTY with option -T and disabling X11 forwarding with -x:
```
ssh -T -x -v -p 2222 user@ip
```


## scp fails with error message `scp: not found` and `lost connection`
The scp command is not installed / not supported on your device. 

### Workaround 1
You can use the following workaround to transfer a file with ssh:
```
cat src_file | ssh -T -x -p 2222 user@ip 'cat > dst_file'
```
The parent directory of `dst_file` must exist.

### Workaround 2
For more comfort, you can use [lsyncd](https://github.com/axkibe/lsyncd) to send modified files automatically to the target. You can find an example configuration file for this purpose at [lsyncd-workaround](https://github.com/thomasrebele/lsyncd-workaround).

