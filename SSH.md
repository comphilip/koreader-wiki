
# Troubleshooting
## ssh fails with error message `packet_write_wait: Connection to ... port 2222: Broken pipe
Try disabling TTY with option -T and disabling X11 forwarding with -x:
```
ssh -T -x -v -p 2222 user@ip
```


## scp fails with error message `scp: not found` and `lost connection`

The scp command is not installed / not supported on your device. You can use the following workaround to transfer a file with ssh:

```
cat src_file | ssh -T -x -p 2222 user@ip 'cat > dst_file'
```
The parent directory of `dst_file` must exist.



