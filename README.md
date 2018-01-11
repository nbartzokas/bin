## Useful binaries

This directory contains useful binaries for deploy and maintenance. Below are other tools worth a look.

##### pssh

	ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
	brew install pssh
	
Execute a command on the remote machine

	pssh 
		-A                    # ask for password
		-h $1                 # hostfile 
		-i                    # display inline
		-o logs/test_out      # std logs
		-e logs/test_err      # err logs
		"echo Hello World"    # command

Execute a local script on the remote machine

	pssh
		-A                    # ask for password
		-h $1                 # hostfile 
		-i                    # display inline
		-o logs/test_out      # std logs
		-e logs/test_err      # err logs
		-x "-T"               # supress pseudo-terminal errors 
		-I < $2               # script
