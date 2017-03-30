Vagrant Plex server with Mounted folders.

v 1.0 (03/30/2017)

Requires: Virtualbox + Vagrant

This was a learning experiment that turned out to be useful.

This will turn up a VM via Vagrant/VirtualBox.

Plex is deployed and setup via an Ansible, 2 mounts are created for tv
and movies folders.

Options via VagrantFile

Network IP to bind plex server. Mount points for tv and movies CPU and
Memory options for the Plex Server

Instructions:

1)  Clone repo to a folder on your machine. (c:\vagrant\plex)

2)  Modify VagrantFile to your liking with your favorite editor
    (c:\vagrant\plex\VagrantFile)

a)  Review the comments for instructions in the file for different
    options.
b)  Review again that all the options are correct. It's important this
    is done correctly.
c)  Save file.

3)  Type vagrant up from a command line or shell, while in the folder.
    This will take some time depending on the speed of your machine.
    Usually \~5mins. ex: start -\> run cmd (enter) cd c:\vagrant\plex
            vagrant up

4)  Wait until you see the Play Recap and you return to a prompt.

5)  Open a web browser and go to the IP you modified in the VagrantFile
    in step 2. (Default is http://192.168.1.99:32400/web a note that
    plex requires this /web on the end of the ip:port to access the web
    panel)

6)  Begin setting up plex in your web browser.
    a)  Give server a name you will recognize.
    b)  If you choose access media outside my home, this may take a
        while to configure a port on your router. If you intend to just
        use this in your home, uncheck this option.
    c)  At the Add Library section, choose /movies for Movies and /tv
        for TV, these link to the folders you specified in step 2 when
        you modified the Vagrantfile.
    d)  Click done.

    It may take some time to scan all your movies and tv if you have a
    lot in these folders. Subsequent launches of the server will be
    faster.

7)  Using a Plex client (Free from www.plex.tv) on your phone, tv,
    tablet, desktop or laptop, you will see the server you named above
    in 6a.

8)  Choose that server and start watching your TV and Movies!

9)  When done watching and you want to turn off the plex server, go back
    into your folder and type vagrant halt. This will cleanly halt the
    server. ex: start -\> run cmd (enter) cd c:\vagrant\plex
            vagrant halt

10) When you want to start the server again, there is no need to
    re-configure, simply go back into the folder and type vagrant up.
    (See Step 3)

Notes: If you make any mistakes or need to make any changes to IP's, CPU
cores, or mount points simply destroy the VM and start again. ex: start
-\> run cmd (enter) cd c:\vagrant\plex
        vagrant destroy vagrant up
