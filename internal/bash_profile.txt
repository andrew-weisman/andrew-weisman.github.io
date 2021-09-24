alias cp='cp -i'
alias mv='mv -i'
alias rm='rm -i'
alias ll='ls -l'

function mkcd() {
    mkdir $1
    cd $1
}

export PS1="\[\e[33m\]\u\[\e[m\]\[\e[33m\]@\[\e[m\]\[\e[33m\]\h\[\e[m\]\[\e[33m\]:\[\e[m\]\[\e[33m\]\w\[\e[m\]\[\e[33m\] \[\e[m\]\[\e[33m\]\[\e[m\]\[\e[33m\]\\$\[\e[m\] "

alias nnd='dirname=`date +"%Y-%m-%d"` && mkdir ~/notebook/${dirname} && cd ~/notebook/${dirname}'
function cdn() {
    cd $(find ~/notebook/ -maxdepth 1 -type d | sort | tail -n 1)
}

function full() {
    files=$(echo "$@" | awk '{gsub(" ",","); print}')

    ncommas=$(echo $files | awk '{x=gsub(",",",");print(x)}')
    
    if [ $ncommas -ge 1 ]; then
        eval "ls -1 $(pwd)/{$files}"
    else
        eval "ls -1 $(pwd)/$files"
    fi
}
