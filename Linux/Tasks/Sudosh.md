
<h2> What is Sudosh? </h2>

<p> Sudosh is a utility package that allows users to actively monitor screen session usage of a user.
Once initated, Sudosh gives the ability to play back the inputed commands from a specefic user.


<h3> Installing Sudosh: </h3>
<p> We need to install GNU Compiler collection, package which contains various libraries compilers for variety of programing langauges.

yum install gcc automake git
Install the c compiler to run the script
Install the automake package to run the make command
git clone https://github.com/squash/sudosh2

./configure
Run the script

make
Run make to initiate the process of compiling the source code and generating executable, artifacts and libraries  
make install
Run make install to implement and install the compiled artifacts, libraries etc…

sudosh -i
Run the command above to initiate an interactive session with Sudosh shell
OUTPUT:
[info]: created directory /var/log/sudosh
[info]: chmod 0733 directory /var/log/sudosh

usermod -s /usr/local/bin/sudosh faze
Edit the user’s shell 

On the root user edit  /etc/shells file and paste the below path
/usr/local/bin/sudosh

ssh faze@192.168.244.163
Log into your server with the configured user.

Run below command on the root user
/usr/local/bin/sudosh-replay







OUTPUT:
From         To           ID
 ====         ==           ==
faze         faze        faze-faze-1691775074-P6rTzVy2kJLzkDuY

The first parameter is the session-ID.

The second parameter is the multiplier. Use a higher value for multiplier to speed up the replay, while "1" is the actual speed.

The third parameter is the max-wait. Where there might have been wait times in the actual session, this parameter restricts waiting for a maximum max-wait seconds, in the example above, 5 seconds.

Logs location: /var/log/sudosh 
Run command on the root user
/usr/local/bin/sudosh-replay faze-faze-1691775074-P6rTzVy2kJLzkDuY 2 0



Alternative to changing the user's shell to utilize Sudosh:
vi /etc/sudoers. Enter the line below
username ALL=(root) NOPASSWD: /usr/local/bin/sudosh

Login to the user and run the command below to activate the user's capture.
/usr/local/bin/sudosh

Error below when running the make command:
/root/capture/sudosh2/missing: line 81: aclocal-1.16: command not found
WARNING: 'aclocal-1.16' is missing on your system.
make: *** [aclocal.m4] Error 127

To resolve issue: Command below installs the necessary files needed to run make.
autoreconf --force --install 
./configure
make
