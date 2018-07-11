# ffnordheide
Site configuration Freifunk-Nordheide e.V.

# Firmware bauen

    cd /your/gluon/build/dir
    
    git clone https://github.com/freifunk-gluon/gluon
    git clone https://github.com/freifunk-nordheide/ffnordheide
    cp -a ffnordheide/ffnh-site gluon/site
    cd gluon
    git checkout v2018.1
    
    # for roamguide:
    git config http.sslVerify "false"
    
    make update
    make GLUON_TARGET=ar71xx-generic V=s
    
    # um schneller, mirt mehreren Kernen zu bauen, wenn alles klappt:
    X=$(expr $(nproc) + 1)
    make GLUON_TARGET=ar71xx-generic -j$X
