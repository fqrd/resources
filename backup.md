## Encode

	sudo apt install gpg

Chose a good password then:

	echo "TEXT_TO_BACKUP" | gpg --symmetric  --cipher-algo AES256 | base64 > seed.txt.gpg.b64

	cat seed.txt.gpg.b64

    sudo apt install qrencode

    sudo apt-get install libpng-dev

    qrencode --output=qr.png "$(cat seed.txt.gpg.b64)"

## Clear your terminal's history

(Your secret could be readable in ~/.bash_history)

    history -c
    rm ~/.bash_history

## Decode

    sudo apt-get install zbar-tools

Read the QR code from a reliable source (try different ones and see if the outputs are different).

- https://zxing.org/w/decode.jspx

Save the seed/output in a file called `output.txt.gpg.b64`

    zbarimg --raw qr.png | base64 --decode | gpg -d

Key in the password.

You should now see the "TEXT_TO_BACKUP" in clear.

(beware some intputs like "x511" might be read as hexadecimal and confuse gpg -d)
(don't forget the `--raw` flag, otherwise zbarimg's output would start with "QR-Code:" which `base64 --decode` won't understand)
