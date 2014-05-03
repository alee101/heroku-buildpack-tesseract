heroku-buildpack-tesseract
===========================
Added the libraries to use Tesseract 3.02.02 on Heroku

This buildpack is built to be used through [heroku-buildpack-multi](https://github.com/ddollar/heroku-buildpack-multi).

## Configuring tesseract for heroku
1. In your app:

        heroku config:add BUILDPACK_URL=https://github.com/ddollar/heroku-buildpack-multi.git
        heroku config:add LD_LIBRARY_PATH=vendor/tesseract-ocr/lib
        heroku config:add TESSDATA_PREFIX=vendor/tesseract-ocr

2. Create a `.buildpacks` file inside your app:

        https://github.com/heroku/_YOUR_MAIN_BUILDPACK
        https://github.com/alee101/heroku-buildpack-tesseract

3. Create a `.profile.d` directory inside your app. In `.profile.d`, create the file `path.sh`:

        PATH=$PATH:$HOME/vendor/tesseract-ocr/bin

## License
MIT License. Copyright 2013 Marco Azimonti.
