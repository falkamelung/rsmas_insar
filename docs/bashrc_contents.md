.bashrc file contents:

```
# User specific aliases and functions
shopt -s expand_aliases

modules_shell="bash"
[ -n module ] && module purge
umask 007

export USER_PREFERRED=famelung
module purge

export CPL_ZIP_ENCODING=UTF-8

alias source_environment='cd $RSMASINSAR_HOME; export PATH=/bin; unset PYTHONPATH; source ~/accounts/platforms_defaults.bash; source setup/environment.bash; export PATH=$ISCE_STACK/topsStack:$PATH; source ~/accounts/alias.bash; source ~/accounts/login_alias.bash; cd -;'

alias s.bw2='export RSMASINSAR_HOME=${WORK2%/*}/stampede2/code/rsmas_insar; source_environment'
alias s.bw2o='export RSMASINSAR_HOME=${WORK2%/*}/stampede2/code_dec23/rsmas_insar; source_environment'

```
Before re-installing the code, rename the directory of your working code to e.g `code_dec23`, so that you can use it with `s.bw2o` with 'o' for old code.


(The `umask` command gives others access to your files: everybody should be able to read/write in your scratch directory whereas nobody should be able to write in your home directory.) 

On Mac:
```
alias s.bw2='export RSMASINSAR_HOME=~/code/rsmas_insar; source_environment'
```
