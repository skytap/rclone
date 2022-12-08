# rclone
Skytap versions of Rclone for AIX and IBM-i

For background information and how these were built read the Rclone on Power PDF

Installation: 

	AIX 7.3 
		(as root)
		run dnf_aixtoolbox.sh 
		copy rclone to /usr/bin/rclone

		create ~/.config/rclone directory
		copy rclone.conf to ~/.config/rclone/rclone.conf
		
	IBM-I 7.4
	    In PASE
	    	• /etc/resolv.conf doesn’t exist 
	    		• Create it
	    			domain test.net
	    			nameserver 208.67.222.222 
	    			nameserver 8.8.4.4
	    			
	    	• /var/ssl is an AIX construct and doesn’t exist ( on linux this would be /etc/ssl )
	    		• Create a soft link to the appropriate locations 
	    			• ln –s /QOpenSys/etc/ssl /var/ssl
		
		    copy rclone to /QOpenSys/usr/bin or /usr/bin
		    create .config/rclone directory
		    copy rclone.conf to .config/rclone/rclone.conf

		    
Once installed configure endpoints with Rclone config

List endpoints with Rclone listremotes

Refer to Rclone documentation for other options and command syntax:

	https://rclone.org/
