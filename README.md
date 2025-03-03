# Qr-code-generation

This is a simple project to generate QR code using python.The main library used in this project is `qrcode`. The `qrcode` library is used to generate the QR code .

## Installation

first you need to install the `qrcode` library using the following command:

# gen_qrcode.py

This Python script uses the `qrcode` library to generate a QR code from given data and save it as an image file.

## Code

```python
import qrcode

def generate_qr_code(data, file_name, pixel_size=240):
    """
    Generate a QR code from the given data and save it to a file.

    Parameters:
        data (str): The data to encode into the QR code.
        file_name (str): The name of the file to save the QR code image to.
        pixel_size (int): The size of each pixel in the QR code. Default is 240.
    """
    qr = qrcode.QRCode(
        version=1,
        error_correction=qrcode.constants.ERROR_CORRECT_L,
        box_size=pixel_size,
    )
    qr.add_data(data)
    qr.make(fit=True)

    # Create an image from the QR code instance
    qr_img = qr.make_image(fill_color="black", back_color="white")

    # Save the image to a file
    qr_img.save(file_name)

# Example usage:
data_to_encode = "https://google.com"
output_file = "google.png"
generate_qr_code(data_to_encode, output_file)




Usage
To use this script, simply import the generate_qr_code function and call it with the data you want to encode and the name of the file you want to save the QR code image to. You can also optionally specify the size of each pixel in the QR code.

For example:

from gen_qrcode import generate_qr_code

data_to_encode = "https://google.com"
output_file = "google.png"
generate_qr_code(data_to_encode, output_file)


This will generate a QR code that encodes the URL "https://google.com" and save it as an image file named "google.png". 
```
