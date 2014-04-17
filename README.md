HashPump
========

A tool to exploit the hash length extension attack in various hashing algorithms

Currently supported algorithms: MD5, SHA1, SHA256, SHA512

Help Menu
=========

    ./HashPump -h
    HashPump [-h help] [-t test] [-s signature] [-d data] [-a additional] [-k keylength]
         HashPump generates strings to exploit signatures vulnerable to the Hash Length Extension Attack.
         -h --help          Display this message.
         -t --test          Run tests to verify each algorithm is operating properly.
         -s --signature     The signature from known message.
         -d --data          The data from the known message.
         -a --additional    The information you would like to add to the known message.
         -k --keylength     The length in bytes of the key being used to sign the original message with.
         Version 1.0.1 with MD5, SHA1, SHA256 and SHA512 support.
         <Developed by bwall(@botnet_hunter)>

Sample Output
=============

    ./HashPump -s 6d5f807e23db210bc254a28be2d6759a0f5f5d99 --data count=10\&lat=37.351\&user_id=1\&long=-119.827\&waffle=eggo -a \&waffle=liege -k 14
    0e41270260895979317fff3898ab85668953aaa2
    count=10&lat=37.351&user_id=1&long=-119.827&waffle=eggo\x80\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x02(&waffle=liege

Compile
=======

    git clone https://github.com/bwall/HashPump.git
    apt-get install g++ libssl-dev
    make
    make install

apt-get and make install require root privileges to run correctly.  The actual requirement is for -lcrypto, so depending on your operating system, your dependencies may vary.

Mentions
========
HashPump has been mentioned in a few write ups.  If you are wondering how you can use HashPump, these are some great examples.
* http://ctfcrew.org/writeup/54
* http://d.hatena.ne.jp/kusano_k/20140310/1394471922 (JP)
* http://conceptofproof.wordpress.com/2014/04/13/plaidctf-2014-web-150-mtgox-writeup/
* http://achatz.me/plaid-ctf-mt-pox/
* http://herkules.oulu.fi/thesis/nbnfioulu-201401141005.pdf
