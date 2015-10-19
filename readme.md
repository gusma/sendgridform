# sendgridform v0.1

A simple contact form using sendgrid's api, and protected with recaptcha (and a very simple verification method).

This was mangled together by [Gustavo Malamud] (http://www.malamud.com.ar) at [hola at gustavomalamud.com.ar](hola@gustavomalamud.com.ar).

## Requisites

This contact form only needs your web server to be able to run html, php (5.4+ on compatible as far as I know) and css. Nothing the year 2015 cannot handle. It's a pretty basic script.

## Caveats / Possible trouble

### Rejection behaviors

As I haven't found a useful option to do away with pesky bots and verify rejections the default action will be for the rejected proposition to come back to the index.html.
Nevertheless you can kill off all rejected requests by either redirecting to another page of your choice or directly killing off all activity on the script.

To do so, please check your js folder, on the verify.php file and check the section of the code we mark below:

```
  else
        {
         	header("Location: ../index.html");
        }

```
### Necessary fields for recaptcha

Please check that both your public and private recaptcha keys are in place. 

The public key is located in the * index.html * file, right before the send button, as shown right here:

```

<!-- WARNING! -->
<!-- PLEASE ENTER YOUR PUBLIC KEY HERE: If you haven't got one, sign up and get your keys at https://www.google.com/recaptcha/admin#list -->

<div class="g-recaptcha" data-sitekey="INSERT YOUR PUBLIC KEY HERE" style="padding-bottom:30px;"></div>

<input class="input-btn animated wow flipInY delay-08s send" type="submit" value="Send"> <!-- Send button-->

```

Whilst your private key can be found at * verify.php *, within:  

```
 //verify captcha
        $recaptcha_secret = "enter your private key here";

```

### Necessary fields for SendGrid

Please do not forget to enter the information for your sendgrid account on the * sender.php * file, right in 

```

<?php
// use actual sendgrid username and password in this section
$url = 'https://api.sendgrid.com/'; 
$user = 'sendgrid user'; // place SG username here
$pass = 'sendgrid password'; // place SG password here


```

Should you have any doubts about this form, please do visit their [demo form] (https://sendgrid.com/blog/create-basic-contact-form-sendgrid-php/) which I pretty much used for my own purposes. 



## To Do List

- Add text verification (Maybe happy.js?)
- Concatenate php files into one
- Find a better solution to the non-validated form

## Apologies

To the purists of PHP, 

To the sorcerors of clean css, 

To the builders of truly good code, 

To the craftsmen of software...

As this is my first repo and collaboration ever for, surprisingly, something that I haven't yet seen posted anywhere.


![Hans Landa] (http://www.gifwave.com/media/21971_idk-shrug-inglorious-basterds-hans-lanza.gif)


## Thanks

To the good friends at [Sendgrid] (http://www.sendgrid.com) for their [demo] (https://sendgrid.com/blog/create-basic-contact-form-sendgrid-php/) on how to build the form.

To all of you having to read this unfinishable dross of code and poor text. 

And to all of you that wish to take this beyond my abilities.

## Legals

The MIT License (MIT)

Copyright (c) 2015 Gustavo Malamud

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
