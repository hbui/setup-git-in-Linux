## Setup Git in Linux (If you have done this in CS 312, you may skip this step)

1. Log into one of the potter boxes using ssh in moba or PuTTY (from Window) or terminal (from your Mac)

2. Create a rsa key using the following command (You may use your email here):

	```
	ssh-keygen -t rsa -b 4096 -C your_email@example.com

	```
	Press Enter when prompted to ‘‘Enter a file in which to save the key...’’ (this saves it to default location).

	Optionally, enter a passphrase and re-enter (I chose to enter) and hit Return. (If you choose to enter a passphrase, 	remember it. It will be the password to unlock your RSA key.) **Please note that it will not show as you type in the 	passphrase**.

	This is similar to what you should see after step 2:
	
	```
	ssh-keygen -t rsa -b 4096 -C hdbui@loyola.edu

	Generating public/private rsa key pair.
	Enter file in which to save the key (/home/hdbui/.ssh/id_rsa):
	Enter passphrase (empty for no passphrase):
	Enter same passphrase again:
	Your identification has been saved in /home/hdbui/.ssh/id_rsa
	Your public key has been saved in /home/hdbui/.ssh/id_rsa.pub
	The key fingerprint is:
	SHA256:QWIAI7u0wvShksgi1vOPtOkm/G08/tQDS4nGuE/FFg4 hdbui@loyola.edu
	The key's randomart image is:
	+---[RSA 4096]----+
	|. o...o .        |
	| o . . o         |
	|.o .   E..       |
	|*o= . o =.o      |
	|O* + . +SO       |
	|*   o o + +      |
	|  .  +.. o o     |
	|   o..O+.   .    |
	|    =*o=o.       |
	+----[SHA256]-----+
	```

3. Enter the command **cat /home/hdbui/.ssh/id_rsa.pub**

	The content of the .pub file will be showed.


	```
	cat /home/hdbui/.ssh/id_rsa.pub
	
	ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAACAQDOUnOHTOMjOZCFg/
	SFvT4v02WagY36w1J6cQDwZ5OIOC1D0LNVMFLMOZzf9i4UnvfymWr0
	H5VGtRgyDWGt84gphDhadzWQ7B12rvU7/gYR5nRC3zHXHwRtSq+xD/
	14xB1RN0BBMNgEdQmX0CMULo+un7NLXmZLy7tYasWaf0LXgxsZo3aF
	Svz6HZSJL14HLSgWP6eLUU8Dfx9IwKzld3kx65UaKXs0nbmO2nGNVJ
	kUNfbAmQ98wuHPd01ou376X9Ml55h+aSkfVAsPyi584SM34UkrVSzN
	dFiYL6t6nOPxjNrolLjY3JYm+oMkghYb1Pao6gernyW7SaT029D6fA
	3XJq8iVuhg2zwcCe62GDsad1pmYZn9UenmvqA+Rq7na+n15KaMdpNE
	A6UpUNUA7voOl0qYFJcCmTm0dXFmlikctLObbSxBfRfFb1fyaXOtPy
	1IjRykn9pMX7vjIBX05OZ0fhdHcIonPEjSSVTl0JFPnP9aF7/7E79I
	HopbxsWx6HnSSjpvIu3DJQT2hEBJagKfX8xRJGARay9ca46UyDC1Q9
	mJ772eOONMoP2Q8TR0aF2jOuaojus9ORSEXSVh5Uh86NvfAJKzzM8p
	ZHzFX0MzgZnCjnh8RUg03yxDrk+gXvS7um/DHbHyTyJoHzYs9B3auC
	+98qEovsoo0UOxJiQ== hdbui@loyola.edu
	```

4. Select and copy the content of the .pub file starting from ssh-rsa.
5. To associate your SSH key with your GitHub account:
	
	```
	a.	Log into your GitHub account
	b.	In the upper right, clock your icon and go to settings
	c.	Find SSH and GPG Keys
	d.	Click "New SSH Key"
	e.	Title it whatever you want to and paste the contents of ~/.ssh/id_rsa.pub (the public key SSH you just copied)
	f.	Click Submit
	```
	
6.	Configure your local git username and email in the temrinal:

	```
	git config --global user.name "FIRST_NAME LAST_NAME"
	git config --global user.email " your_email@example.com "
	
	```

7. Quickly check to see everything works correctly by running **ssh -T git@github.com** command

	```
	ssh -T git@github.com
	Enter passphrase for key '/home/hdbui/.ssh/id_rsa': 
	Hi hbui! You've successfully authenticated, but GitHub does not provide shell access.
	```

	That's is, you should never have to do that again. Let's test it to make sure it works.

## Testing your connection to GitHub

1.	Once logged into the potter boxes, create a new directory and make sure you are working in it:
		
	```
	a.	mkdir 366
		i.	The mkdir command makes a new directory
			(see what directory you are currently in by using pwd command)
	b.	cd 366
		i.	The cd command changed the directory you are currently in.
			Try typing pwd again. Typing cd .. will move you back, but don't do that now. 
	```

2.	Go to your browswer, find the 366 examples Repo on Moodle (under Resources) and click the invite link and accept it if you have not done so.

3.	Log into your GitHub account and navigate to the assignment (This is likely already up on screen already after accepting the assignment.)

4.	Click the "Code" button on the right side.

5.	Select SSH.

6.	Copy the URL provided (It should be something like **git@github.com:hbui-cs366-S23/366examples...**)

7.	Go back to the termimal, clone a local copy using the following command
	**git clone \<pasted URL from above>**
	
	It should look similar to this:

	```
	git clone git@github.com:hbui-cs366-S23/366examples.git
	```

8.	You should have seen it do some things. Check to see if the files were cloned. 

	```
	a.	ls
		i.	The ls command lists everything in a directory, you should see
		your newly created directory there.
		Do you remember how to change to that directory? (Hint:, see step 1. b.)
	```
	
##Using git
In the future, to update your class examples repo, navigate there and then use "git pull" and other git commands.

1.	Log into a potter box of your choice.

2.	Navigate to the directory
		
	```
	a.	cd cs366
	b.	cd <class-examples-directory>
	c.	git pull
	d.	If this were an assignment, you might also do the following:
		i.	Edit/create some files (see the "vi cheatsheet" under resources)
			1.	Perhaps add your name as a comments to your C source file

		ii.	 git add filename
		iii.	git commit filename -m "<commit message goes here>"
		iv.	git push
	```

Hopefully, you can see your edits on GitHub and know that this worked!
