# reverseproxy issues

Small Stack to demonstrate and hopefully help fix reverse proxy issue im having with subpaths.

I would like to use docmost behind a ngnix reverse proxy with the subpath docmost ( its a real pain to get any additional subdomains internally... )

Setup:

- Top Level Domain: myhostname.fake ( testing on my local network with DNS rewrites via adguard dns)
- subpath: docmost
- <div>APP_URL: http://myhostname.fake/docmost/</div>

Results:

- url loads - however, i get a 404 from docmost

[![image.png](https://github.com/securenotebook/testdocmostreverseproxy/blob/main/pics/docmost404.png)](https://github.com/securenotebook/testdocmostreverseproxy/blob/main/pics/docmost404.png)

From IP its loads fine
[![image.png](https://github.com/securenotebook/testdocmostreverseproxy/blob/main/pics/docmostip.png)](https://github.com/securenotebook/testdocmostreverseproxy/blob/main/pics/docmostip.png)

Note APP\_URL strips the subpath /docmost/ from the the value set in the docker compose


Generated HTML

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png">
    <link rel="icon" type="image/png" sizes="16x16" href="/favicon-16x16.png">
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Docmost</title>
    <script type="module" crossorigin src="/assets/index-B4n9gZBA.js"></script>
    <link rel="stylesheet" crossorigin href="/assets/index-Buo4Gbpv.css">
  </head>
  <body>
    <div id="root"></div>

    <script>window.CONFIG={"ENV":"production","APP_URL":"http://myhostname.fake","CLOUD":false,"FILE_UPLOAD_SIZE_LIMIT":"50mb"};</script>

  </body>
</html>
```