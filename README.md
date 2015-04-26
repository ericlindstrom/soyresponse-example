# soyresponse-example

## Setup

1. Install

    npm install
    npm install --save ericlindstrom/soyresponse

2. Replace view engine setup with:

    var soyresponse = require('soyresponse');
    
    var soyResponseOptions = {
      allowJson: true,
      xssiPrefix: '])}while(1);</x>'
    };
    app.use(soyresponse(__dirname, soyResponseOptions));

3. Replace views with soy templating. see `views` folder

4. Change all render methods to use new templates `example.views`, see routes 
folder and error handler routes.

## Testing JSON Response

With the server running, curl the URL with the `X-Requested-With` header.

    $ curl http://localhost:3000/ -H 'X-Requested-With: XMLHttpRequest'
    > ])}while(1);</x>{"title":"Express"}


