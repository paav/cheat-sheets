# Package Managers

## Debian

Search installed package by name

    aptitud search '~i mysql'

## Arch

Update all packages:

    pacman -Syu

# Misc.

Archive book notes

    find books/ -name '*_notes.txt' | tar -czvf book-notes.tar.gz -T - && mv book-notes.tar.gz /media/4shared/backup/

Restore files with dar

    dar -x backup/2016-04-04T23-00_02_alex_diff -R tmp/ -v -g .bash_history -K Itkljy73
    dar -x backup/2016-05-09T23-00_02_alex_diff -R tmp/restore/ -v -g Anki -K Itkljy73

Record audio

To record:

    sleep 5; arecord -f S16_LE -r 48000 -D hw:1,0 guitar.wav

To play:

    aplay guitar.wav

Download English pronunciation

    curl -O https://ssl.gstatic.com/dictionary/static/sounds/de/0/embrace.mp3

Add numbers to filenames

    i=1; for f in *.JPG; do mv "$f" 2015-12-22_krasilnikova-passport_0"$i".jpg; let i=i+1; done

Copy images from digital camera

	gphotofs ~/camera/ && feh -A "cp %f ./%n" ~/camera/**/*JPG && fusermount -u ~/camera

Sort dirs by size

    du -sh projects/* | sort -hr

Make screenshot

    (sleep 5; imlib2_grab screenshot.png) &

    sleep 5
    imlib2_grab screenshot.png &

Set up subtitles

    for s in tmp/subs/*; do
        v=$(ls video/modern*s05e${s:27:2}*)
        cp "$s" "${v[0]/avi/srt}"
    done

Start mplayer

    mplayer -vf scale -zoom -xy 900 -softvol -softvol-max 500 -volume 100 \
        -aid 2 video/*middle*s03e01*

Write CD

Create iso:

    genisoimage -V "carcd" -J -r -o carcd.iso music/carcd/

Erase disk:

    wodim -v dev=/dev/sr0 blank=fast

Write disk:

    wodim -v -sao dev=/dev/sr0 carcd.iso

