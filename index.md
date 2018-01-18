## Setting Up Your Computer

The following packages / programs need to be installed on your laptop to be able to carry out the lab work assigned during the workshop. Please note that it is the participants' responsibility to install these on your respective systems.

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

```Carefully read the instructions the script prints to your terminal since there might be special instructions for your operating system.

Once you've downloaded it, just run:
$ bash install_script.sh
$ export PATH=/path/to/YT_DEST/bin:$PATH

where YT_DEST will be the folder created by the install script containing a yt installation (usually yt-conda).
```

now append your ~/.bashrc with: 

`export PATH=/path/to/YT_DEST/bin:$PATH` 

`export LD_LIBRARY_PATH=path/to/YT_DEST/lib:$LD_LIBRARY_PATH`

for example, if you installed `yt` to `/home/john/software/yt_3_4/`, the above lines will change to:

``` export PATH=/home/john/software/yt_3_4/yt-conda/bin:$PATH 

export LD_LIBRARY_PATH=/home/john/software/yt_3_4/yt-conda/lib:$LD_LIBRARY_PATH
``` 
Last but not least, don't forget to source your `bashrc`:

```source ~/.bashrc
```  


### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/simulationASI2018/Cosmological-Simulations/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
