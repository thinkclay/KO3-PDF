# PDF Module for Kohana 3.3

Extension for Kohana's View class that renders as a PDF instead of HTML. Uses [DOMPDF](https://github.com/dompdf/dompdf) to render normal HTML views as PDF Files.
**Please report all bugs related to PDF rendering there**

<br />

## Installation

Install DOMPDF using the submodule:

```php
cd modules/pdf
git submodule update --init
```

This will install DOMPDF to `vendor/dompdf/dompdf` from the [DOMPDF Git mirror](http://github.com/dompdf/dompdf). For DOMPDF to work properly, the `fonts` directory must be writable:

    # Replace "http" with your web server user and group!
    chown http:http vendor/dompdf/dompdf/lib/fonts
    
    # An insecure alternative:
    chmod 0777 vendor/dompdf/dompdf/lib/fonts

<br />

## Usage

Placed in a controller action:

```php
// Load a view using the PDF extension
$pdf = View_PDF::factory('pdf/example');

// Use the PDF as the request response
$this->request->response = $pdf;

// Display the PDF in the browser as "my_pdf.pdf"
// Remove "inline = TRUE" to force the PDF to be downloaded
$this->request->send_file(TRUE, 'my_pdf.pdf', ['inline' => TRUE]);
```

=======
This module is released under an [MIT opensource license](http://opensource.org/licenses/MIT)








