# firefox-docker

After losing most of a days work fighting to resolve "Error code: ssl_error_weak_server_ephemeral_dh_key", I gave up.

An internal web application in my office returns this lovely error, and Fedora says Ell No!!  For some reason Debian systems don't give a crap, so...

I put together a docker container to run Debian FireFox.  Now I can access the ticketing system at work to enter a ticket for the SAs to fix the certs on the server that runs their ticketing system.

# And then I found a work-around...
I found a FF extenstion to get around my issue https://github.com/sid77/strict-ssl3-config
The extension toggles quite a few security.ssl3.* flags, but it made the problem go away.  I used the extension as a starting point to find that I only needed to set `security.ssl3.dhe_rsa_aes_128_sha` to false.

Well... at least I figured out how to run a GUI application from within a docker container ;)
