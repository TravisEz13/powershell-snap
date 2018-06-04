FROM ubuntu:16.04 AS base

ADD https://github.com/PowerShell/PowerShell-Snap/blob/master/assets/thirdPartyNoticeHeader.txt tpnHeader.txt

ENV thirdPartyNoticeFile="thirdPartyNotices.txt"
RUN cat tpnHeader.txt > $thirdPartyNoticeFile; rm tpnHeader.txt ; \
    find / -type f -name 'copyright' -print | while read filename; do   \
        libname=$(dirname $filename | sed 's,^\(.*/\)\?\([^/]*\),\2,') ; \
        echo '' ; \
        echo '---------------------------------------------' ;\ 
        echo "Package - $libname" ;\
        echo '---------------------------------------------' ;\
        cat "$filename" ;\
      done >> $thirdPartyNoticeFile
