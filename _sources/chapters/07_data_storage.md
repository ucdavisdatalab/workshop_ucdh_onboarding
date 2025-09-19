# Data Storage
Protected data can't be taken off the UCDH premises and if you're using an ACE VM it will have modest storage that will eventually be erased and returned to the general pool. So it is necessary to have some persistent storage that can store protected information, other than the VM hard drive. UCDH offers a couple of options here. The most secure but least convenient is to store the data on the UCDH network drive, and the more convenient but less secure storage option is OneDrive.

## Network Drive
The UCDH network drive is a Windows NT-style filesystem that has managed access for users with valid permissions. You can access via the File Browser it if you're using a UCDH-supplied computer, and from the ACE VM it is accessible via Samba, which should be installed by default in your shell environment. To access the network drive via Samba, use the `smbclient` command line tool like so:

```
smbclient  \\\\hshome\\shared -U'hs\wbrooks'
```

but replacing my username (`hs\wbrooks`) by your own. This will open an interactive Samba session. In order to browse an dmove files you need to use Samba commands in the interactive session – [see the guide here](https://github.com/noobosaurus-r3x/Cheat-sheets/blob/main/SMBClient%20Cheat%20Sheet.md#3-interactive-commands) for the interactive commands.

## OneDrive
UCDH generally uses Microsoft web services. Their cloud storage service is OneDrive (comparable to Box, which is used by the Davis campus.) You can get started with OneDrive by going to [https://ucdavis365-my.sharepoint.com](https://ucdavis365-my.sharepoint.com). Strangely, that seems to work with my Davis campus login.

I have never gotten a definitive answer on whether the cloud storage used by UCDH's OneDrive instance is owned by UCDH and on their property. As such, I never assume that it is secure enough to hold PHI and PII. Sometimes you will work with a UCDH researcher who is confident they know the answer, but they don't all agree with each other. So be cautious and don't be the one who exposes sensitive patient information.