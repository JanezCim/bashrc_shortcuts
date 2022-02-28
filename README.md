## To insert this file into your bashrc, clone this file into your ~ directory and execute this command:  

	cd
	git clone https://github.com/JanezCim/bashrc_shortcuts.git
	sudo cp bashrc_shortcuts/config ~/.ssh/config
	echo -e "if [ -f $HOME/bashrc_shortcuts/custom_commands ]; then\n\t. $HOME/bashrc_shortcuts/custom_commands\nfi" >> ~/.bashrc
	source ~/.bashrc


## (optional) Installation of ROS1 multimaster (as of 10.3.2021)
	pip install --upgrade pip 

Note: on qemu `sudo -H pip2 install --upgrade pip` needed instead

if you have a locale problem here try fixing it with: `export LC_ALL=C`, otherwise continue with

	mkdir -p ~/multimaster_ws/src
	cd ~/multimaster_ws/src
	git clone https://github.com/fkie/multimaster_fkie.git multimaster
	rosdep update
	rosdep install -i --as-root pip:false --reinstall --from-paths multimaster
	pip install pycryptodome
	sudo apt install avahi-daemon python-avahi
	sudo apt install python-gobject
	cd ..
	catkin build fkie_multimaster

add the sourcing multimaster workspace to .bashrc
	
	echo "source ~/multimaster_ws/devel/setup.bash" >> ~/.bashrc
