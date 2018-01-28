# Setting Up Your Computer

The following packages / programs need to be installed on your laptop to be able to carry out the lab work assigned during the workshop. Please note that it is the participants' responsibility to install these on your respective systems. You are strongly encouraged to use Linux based operating systems.

- openssl-devel
- uuid-devel
- readline-devel
- ncurses-devel
- zip
- gcc-{,c++,gfortran}
- make
- patch
- git
- yt (>3.4.0, but not yt 2.X versions)

You can accomplish this in Ubuntu by executing:

`$ sudo apt-get install gcc gcc-c++ gcc-gfortran make patch zip git`

`$ sudo apt-get install ncurses-devel uuid-devel openssl-devel readline-devel`

And in Fedora 24 and above by executing:

`$ sudo dnf install gcc gcc-c++ gcc-gfortran make patch zip git`

`$ sudo dnf install ncurses-devel uuid-devel openssl-devel readline-devel`

For Fedora 23 and below by executing:

`$ sudo yum install gcc gcc-c++ gcc-gfortran make patch zip git`

`$ sudo yum install ncurses-devel uuid-devel openssl-devel readline-devel`

For installing `yt`, please use the `install_script.sh` included in this git repository.

Download here 
[install_script.sh](https://simulationasi2018.github.io/Cosmological-Simulations/install_script.sh)

Carefully read the instructions the script prints to your terminal since there might be special instructions for your operating system.

Once you've downloaded it, just run:

`$ bash install_script.sh`

`$ export PATH=/path/to/YT_DEST/bin:$PATH`

where YT_DEST will be the folder created by the install script containing a yt installation (usually yt-conda).

now append (_if you wish to make this Python distribution as the default Python distribution. Otherwise, go to the next section. **We recommend to use a virtual environment, which will be discussed below**_) your ~/.bashrc with: 

`export PATH=/path/to/YT_DEST/bin:$PATH` 

`export LD_LIBRARY_PATH=path/to/YT_DEST/lib:$LD_LIBRARY_PATH`

for example, if you installed `yt` to `/home/reju/software/yt_3_4/`, the above lines will change to:

`export PATH=/home/reju/software/yt_3_4/yt-conda/bin:$PATH` 

`export LD_LIBRARY_PATH=/home/reju/software/yt_3_4/yt-conda/lib:$LD_LIBRARY_PATH`

Last but not least, don't forget to source your `bashrc`:

`$ source ~/.bashrc`

## Important!

The above steps will make the current installation of python and dependent package versions as your default python. This may lead package version conflict with your ongoing projects. **_So we recommend you to use the virtual environment of the `YT` for the lab section._** 

### What is a virtual environment?

At its core, the main purpose of Python virtual environments is to create an isolated environment for Python projects. This means that each project can have its own dependencies, regardless of what dependencies every other project has.

Consider the following scenario where you have two projects - ProjectA and ProjectB, both of which have a dependency on the same library, ProjectC. The problem becomes apparent when we start requiring different versions of ProjectC. Maybe ProjectA needs v1.0.0, while ProjectB requires the newer v2.0.0, for example.

So, in our little example above, we’d just need to create a separate virtual environment for both ProjectA and ProjectB and we’d be good to go. Each environment, in turn, would be able to depend on whatever version of ProjectC they choose, independent of the other.

The great thing about this is that there are no limits to the number of environments you can have since they’re just directories containing a few scripts. Plus, they’re easily created using the `venv` command line tool.

### How to make virtual environments of `YT`

- Make an alias (An alias is a way to make a complicated command or set of commands simple) in `~/.bashrc` for the fresh installation of `python` and `pip`. 

**Syntax:**

`alias pythonYT='/home/reju/software/yt_3_4/yt-conda/bin/python3.6'`

`alias pipYT='/home/reju/software/yt_3_4/yt-conda/bin/pip'`


assuming that the installation path of `yt` is `/home/reju/software/yt_3_4/` as discussed above. 

- Open your `~/.bashrc` with your favourite text editor and append the `~/.bashrc` with above two lines. 

- `$ source ~/.bashrc`

- Now, for fresh project with `yt`

1. `$ mkdir yt_project`
2. `$ cd yt_project`
3. `$ pythonYT -m venv yt-x86_64/`
4. `$ source yt-x86_64/bin/activate`

_Notice how your prompt is now prefixed with the name of your environment (`yt-x86_64`, in our case). This is the indicator that `yt-x86_64` is currently active, which means the python executable will only use this environment’s packages and settings._

- `(yt-x86_64) $ which python`, Now you can  be sure that which python is active

- When done with the environment, we need to go back to the system context by executing deactivate:

`(yt-x86_64) $ deactivate`

Now your shell session is back to normal, and the `python` command refers to the global Python install. Remember to do this whenever you’re done using a specific virtual environment. 

- If you want to do something in this project later, just go to the project directory (`cd`), and activate the virtual environment again:

`$ source yt-x86_64/bin/activate`


