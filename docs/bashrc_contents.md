.bashrc file contents:

```
# User specific aliases and functions
shopt -s expand_aliases

modules_shell="bash"
[ -n module ] && module purge
umask 007

export USER_PREFERRED=famelung
module purge

alias s=source
export CPL_ZIP_ENCODING=UTF-8

alias source_environment='cd $RSMASINSAR_HOME; export PATH=/bin; unset PYTHONPATH; source ~/accounts/platforms_defaults.bash; source setup/environment.bash; export PATH=$ISCE_STACK/topsStack:$PATH; s ~/accounts/alias.bash; s ~/accounts/login_alias.bash; cd -;'

alias s.bw2='export RSMASINSAR_HOME=${WORK2%/*}/stampede2/code/rsmas_insar; source_environment'
alias s.bt='export RSMASINSAR_HOME=/tmp/rsmas_insar; source_environment'

```
(The `umask` command gives others access to your files: everybody should be able to read/write in your scratch directory whereas nobody should be able to write in your home directory.) 
