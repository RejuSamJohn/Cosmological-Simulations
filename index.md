# Setting Up Your Computer

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

## Important!

The above steps will make the current installation of python and dependent package versions as your default python. This may lead package version conflict with your ongoing projects. **_So we recommend you to use the virtual environment of the `YT` for the lab section._** 

### What is a virtual environment?

At its core, the main purpose of Python virtual environments is to create an isolated environment for Python projects. This means that each project can have its own dependencies, regardless of what dependencies every other project has.

Consider the following scenario where you have two projects - ProjectA and ProjectB, both of which have a dependency on the same library, ProjectC. The problem becomes apparent when we start requiring different versions of ProjectC. Maybe ProjectA needs v1.0.0, while ProjectB requires the newer v2.0.0, for example.

So, in our little example above, we’d just need to create a separate virtual environment for both ProjectA and ProjectB and we’d be good to go. Each environment, in turn, would be able to depend on whatever version of ProjectC they choose, independent of the other.

The great thing about this is that there are no limits to the number of environments you can have since they’re just directories containing a few scripts. Plus, they’re easily created using the `venv` command line tool.

### How to make virtual environments of `YT`

1) Make an alias (An alias is a way to make a complicated command or set of commands simple) in `~/.bashrc` for the fresh installation of python and pip via `yt`. 

**Syntax:**

```alias pythonYT='/home/john/software/yt_3_4/yt-conda/bin/python3.6'

alias pipYT='/home/john/software/yt_3_4/yt-conda/bin/pip'
```

assuming that the installation path is ` /home/john/software/yt_3_4/` as discussed above. 

- Open your `~/.bashrc` with your favourite text editor and append the `~/.bashrc` with above two lines. 
