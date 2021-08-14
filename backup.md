## Encode

	sudo apt install gpg

Chose a good password then:

	echo "TEXT_TO_BACKUP" | gpg --symmetric  --cipher-algo AES256 | base64 > seed.txt.gpg.b64

    sudo apt install qrencode

    qrencode --output=qr.png "$(cat seed.txt.gpg.b64)"

(if you have troubles creating .png, `sudo apt-get install libpng-dev`)

## Clear your terminal's history

(Your secret could be readable in ~/.bash_history)

    history -c
    rm ~/.bash_history

## Decode

    sudo apt-get install zbar-tools

    zbarimg --raw qr.png | base64 --decode | gpg -d

Key in your password. (copy/paste to avoid the timeout)

You should now see the "TEXT_TO_BACKUP" in clear.

(don't forget the `--raw` flag, otherwise zbarimg's output would start with "QR-Code:" which `base64 --decode` won't understand)

## Another way to decode QR Code From file

- https://zxing.org/w/decode.jspx

## Decode from Webcam

    sudo apt install qtqr

Once installed plug-in your camera, launch the program and select "Decode from Webcam" (be sure to remain steady).
