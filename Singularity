Bootstrap: shub
From: CNC-UMCG/cnc_base


%post
	add-apt-repository universe
	apt-get update -y
	
	apt-get install -y tcsh xfonts-base python-qt4       \
        	                gsl-bin netpbm gnome-tweak-tool   \
                	        libjpeg62 xvfb xterm vim curl     \
                        	gedit evince                      \
	                        libxm4 build-essential	
				
	cd
	curl -O https://afni.nimh.nih.gov/pub/dist/bin/linux_ubuntu_16_64/@update.afni.binaries
	tcsh @update.afni.binaries -package linux_ubuntu_16_64  -do_extras
	export R_LIBS=$HOME/R
	
	################
	# Install R   #
	################
	
	mkdir $R_LIBS
	echo 'export R_LIBS=$HOME/R' >> ~/.bashrc
	curl -O https://afni.nimh.nih.gov/pub/dist/src/scripts_src/@add_rcran_ubuntu.tcsh
	tcsh @add_rcran_ubuntu.tcsh

	rPkgsInstall -pkgs ALL
