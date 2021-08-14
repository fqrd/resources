# Linux (Ubuntu 20.04LTS)

## Encode

	sudo apt install gpg

Chose a good password then:

	echo "SECRET" | gpg --symmetric  --cipher-algo AES256 | base64 > secret.txt

    sudo apt install qrencode

    qrencode --output=qr.png "$(cat secret.txt)"

(if you have troubles creating .png, `sudo apt-get install libpng-dev`)

## Clear your terminal's history

(Your secret could be readable in ~/.bash_history)

    history -c
    rm ~/.bash_history

## Decode from a file

    sudo apt-get install zbar-tools

    zbarimg --raw qr.png | base64 --decode | gpg -d

Key in your password. (copy/paste to avoid the timeout)

You should now see the "SECRET" in clear.

(don't forget the `--raw` flag, otherwise zbarimg's output would start with "QR-Code:" which `base64 --decode` won't understand)

OR

1. Go to [zxing.org](https://zxing.org/w/decode.jspx) and upload the desired file.

2. Copy/paste the output in a file called `output.txt` and execute the following command.

    cat output.txt | base64 --decode | gpg -d
3. Key in your password. Done.

## Read from a Camera/Webcam

    sudo apt install qtqr

Once installed plug-in your camera, launch the program and select "Decode from Webcam" (be sure to remain steady). To decode the output, follow along from step 2 above.
