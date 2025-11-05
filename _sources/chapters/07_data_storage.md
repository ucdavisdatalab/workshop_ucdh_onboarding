# Data Storage
Protected data can't be taken off the UCDH premises and if you're using an ACE VM it will have modest storage that will eventually be erased and returned to the general pool. So it is necessary to have some persistent storage that can store protected information, other than the VM hard drive. UCDH offers a couple of options here. The most secure but least convenient is to store the data on the UCDH network drive, and the more convenient but less secure storage option is Sharepoint or One Drive.

## Network Drive
The UCDH network drive is a Windows NT-style filesystem that has managed access for users with valid permissions. If there is a folder on the network drive that you need to access, you'll [request access via the Service Now catalog](https://ucdh.service-now.com/itss?id=sc_cat_item&sys_id=3b274cbadb83d3c045883220ad961940).

You can access the notwork drive via the File Browser it if you're using a UCDH-supplied computer ([see instructions in the knowledge base](https://ucdh.service-now.com/itss?id=kb_article_view&sysparm_article=KB0023100)). From an ACE VM running Linux, the notwork drive is accessible via Samba, which should be installed by default. Use the `smbclient` command line tool to access the network drive via Samba, like so:

```
smbclient  \\\\hshome\\shared -U'hs\wbrooks'
```

but replacing my username (`hs\wbrooks`) by your own. This will open an interactive Samba session. In order to browse an dmove files you need to use Samba commands in the interactive session – [see the guide here](https://github.com/noobosaurus-r3x/Cheat-sheets/blob/main/SMBClient%20Cheat%20Sheet.md#3-interactive-commands) for the interactive commands.

## One Drive and Sharepoint
UCDH generally uses Microsoft web services. Their cloud storage service are called One Drive and Sharepoint (both are comparable to Box, which is used by the Davis campus.) There are subtle differences between the two: One Drive files are owned by a user and are stored in that user's data container on the Microsoft data servers. Sharepoint files are organized into **sites**, each of which is owned by a team. Even when a team has only one person on it, that person doesn't individually own the files in the site. Administrators of their organization can add people to the team and those new people immediately have access to the data on the site. While I have used the lower-case 't' to refer to a team as a group of people, Sharepoint is integrated with Microsoft Teams the software product (notice the capital 'T') so that each team in Teams has a Sharepoint site for collective data storage. You can also create sites that aren't linked to Teams.

You can get started with One Drive by going to [https://ucdavis365-my.sharepoint.com](https://ucdavis365-my.sharepoint.com). Strangely, that seems to work with my Davis campus login. The link to view the web interface for Sharepoint is [https://ucdavis365.sharepoint.com/_layouts/15/sharepoint.aspx](https://ucdavis365.sharepoint.com/_layouts/15/sharepoint.aspx).
