## Encode

	sudo apt install gpg

Chose a good password then:

	echo "TEXT_TO_BACKUP" | gpg --symmetric  --cipher-algo AES256 | base64 > seed.txt.gpg.b64

	cat seed.txt.gpg.b64

(Generate a QR code from the output with qtqr or use an online tool to create it. Beware qtqr isn't 100% reliable when it comes to "decode from file")

	sudo apt install qtqr

OR

    sudo apt install qrencode

    sudo apt-get install libpng-dev

    qrencode -o img.png $(cat seed.txt.gpg.b64)

## Decode



    sudo apt-get install zbar-tools

Read the QR code from a reliable source (try different ones and see if the outputs are different).

- https://zxing.org/w/decode.jspx

- Qtqr and Zbar output's are too long somehow.

Save the seed/output in a file called `output.txt.gpg.b64`

    zbarimg --raw img.png > output.txt.gpg.b64

(beware some intputs like "x511" would be read as hexadecimal and confuse gpg -d)
(if any problems, make sure the file is in simple UTF8 - without BOM)

	cat output.txt.gpg.b64 | base64 --decode | gpg -d

Key in the password.

You should now see the "TEXT_TO_BACKUP" in clear.
