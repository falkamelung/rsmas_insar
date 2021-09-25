.bashrc file contents:

```
# User specific aliases and functions
shopt -s expand_aliases

modules_shell="bash"
[ -n module ] && module purge
umask 002

export USER_PREFERRED=famelung
#module purge

alias s=source
export CPL_ZIP_ENCODING=UTF-8
alias s.bw2='export RSMASINSAR_HOME=$(dirname $WORK2)/stampede2/code/rsmas_insar; cd $RSMASINSAR_HOME; s ~/accounts/platforms_defaults.bash; s setup/environment.bash; export PATH=$ISCE_STACK/topsStack:$PATH; s ~/accounts/alias.bash; s ~/accounts/login_alias.bash; cd -;'
```
(The `umask` command gives others access to your files: everybody should be able to read/write in your scratch directory whereas nobody should be able to write in your home directory. We shoould aim for `module purge` to be independent of existing libraries but this does not work yet.). 
