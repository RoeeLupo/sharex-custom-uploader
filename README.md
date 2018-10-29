# sharex-custom-uploader
A PHP script I modified for uploading custom sharex files to your own webserver

# Setup
First we start by uploading the content of the github repo to the root of our website

Next is the configuration file, found in /captures/config.php here there are a few key settings

```
/* This is a secure key that only you should know, an added layer of security for the image upload */
  'secure_key' => 'somerandomlongstringoftextforkey',

/* This is the url your output will be, usually http://www.domain.com/u/, also going to this url will be the gallery page */
  'output_url' => 'http://yourdomain.com/captures/',

/* This is a redirect url if the script is accessed directly */
  'redirect_url' => 'http://yourdomain.com/captures/',

/* This is a list of IPs that can access the gallery page (Leave empty for universal access) */
  'allowed_ips' => array(),

/* Page title of the gallery page */
  'page_title' => 'My Upload Site',

/* Heading text at the top of the gallery page */
  'heading_text' => 'Uploading Site',
  ```
  
  # ShareX configuration
  Next we need to setup our ShareX to use the custom uploader

```
1. From the ShareX main application we go to Destinations > Destination Settings
2. Scroll down to 'custom uploaders' add a new profile
3. Request type POST, the url should be http://yourdomain.com/upload.php
4. File form name: "d" (without quotation marks)
5. Arguments are:
    - key, this should be set to the 'secure key' you set in your config.php
    - name, this is how the files will be named, for mine, I use '%rn%rn%rn%rn%rn%rn'
6. The setup is now complete, test your uploader and it 'should' work!
```

# Preview

![Preview of gallery](https://cdn.mrsheldon.me/files/670022.png)


