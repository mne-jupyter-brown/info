# Workshop Information


## Official Materials  

https://github.com/jasmainak/mne-workshop-brown - maintained by Mainak Jas

## Computing resources

As a member of this organization, you are enabled to login into the workshop's [Jupyter Hub](https://ccv.jupyter.brown.edu)

After loging in, please select the MNE-Workshop spawner. The materials are auto-pulled into the hub under `mne-gitpuller` 

**Access will only be granted during the duration of the workshop. No persistant storage of your materials is guaranteed**


## Advanced git users

`mne-gitpuller` is synched using a tool called [nbgitpuller](https://github.com/jupyterhub/nbgitpuller) which magically tries to merge conflicts, but assumes one-way sync

### Merging behavior

nbgitpuller is designed to hide that git is being used
underneath, and to pull content one way from a source and modifying it -
not pushing it back.
It makes the following opinionated decisions.

1. If content has changed in both places, prefer local changes over remote changes.
2. If a file was deleted locally but present in the remote, remote file is restored
   to local repository. This allows users to get a 'fresh copy' of a file by
   just deleting the file locally & clicking the link again.
3. If a file exists locally but is untracked by git (maybe someone uploaded it manually),
   then rename the file, and pull in remote copy.
   
**You should NOT use git directly inside `mne-gitpuller`, since the assumptions
   and design of nbgitpuller will surprise you in unexpected ways if you are pushing with
   git but pulling with nbgitpuller.**

**If you wish to keep your content after the workshop, and you know git, you can fork https://github.com/jasmainak/mne-workshop-brown, and clone it directly into the hub**

## Merging conflicts

If a merging conflict arises, you can simply delete the file, and force a re-pull.. To do so open launch the terminal inside your JupyterHub and tye `gitpuller https://github.com/jasmainak/mne-workshop-brown.git master mne-gitpuller`

To remove a folder you need to either empty it's contents first or force via the terminal `rm -rf myfoldertodelete`
