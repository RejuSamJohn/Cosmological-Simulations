## Setting Up Your Computer

The following packages / programs need to be installed on your laptop to be able to carry out the lab work assigned during the workshop. Please note that it is the participants' responsibility to install these on your respective systems. You are strongly encouraged to use Linux based operating systems.

- Python (>3.4) (but not Python 2.X versions)
- openssl-devel
- uuid-devel
- readline-devel
- ncurses-devel
- zip
- gcc-{,c++,gfortran}
- make
- patch
- git
- yt (3.4.0)

For installing `yt`, please use the `install_script.sh` included in this git repository.

Download here 
[install_script.sh](https://simulationasi2018.github.io/Cosmological-Simulations/install_script.sh)

Carefully read the instructions the script prints to your terminal since there might be special instructions for your operating system.

Once you've downloaded it, just run:

`$ bash install_script.sh`

`$ export PATH=/path/to/YT_DEST/bin:$PATH`

where YT_DEST will be the folder created by the install script containing a yt installation (usually yt-conda).

now append your ~/.bashrc with: 

`export PATH=/path/to/YT_DEST/bin:$PATH` 

`export LD_LIBRARY_PATH=path/to/YT_DEST/lib:$LD_LIBRARY_PATH`

for example, if you installed `yt` to `/home/john/software/yt_3_4/`, the above lines will change to:

`export PATH=/home/john/software/yt_3_4/yt-conda/bin:$PATH` 

`export LD_LIBRARY_PATH=/home/john/software/yt_3_4/yt-conda/lib:$LD_LIBRARY_PATH`

Last but not least, don't forget to source your `bashrc`:

`source ~/.bashrc`


