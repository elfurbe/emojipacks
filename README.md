# emojipacks

> CLI to bulk upload emojis to your Slack!

```bash
$ git clone https://github.com/elfurbe/emojipacks.git
$ cd emojipacks
$ make
```

## Usage

There is only one command:

```bash
$ emojipacks
```

It'll ask you a few questions:

```bash
Slack subdomain: 20percentclub
Email address login: andyjiang@gmail.com
Password: *********
Path or URL of Emoji yaml file: ./packs/futurama.yaml
```

Then, let it work its magic:

```bash
Starting import
Got tokens
Logged in
Upload crumb is s-1437797544-90b75206a7-☃
Getting emoji page
Uploading bender with http://i.imgur.com/7zYM751.png
Uploading amywong with http://i.imgur.com/DgKkcCi.png
 .
 .
 .
Uploading hypnotoad with http://i.imgur.com/o7tyjxN.gif
Uploaded emojis
```

Note that the emoji pack to upload can be a **path** to a yaml file on your machine or a **URL**, like [http://www.emojipacks.com/packs/food.yaml](http://www.emojipacks.com/packs/food.yaml).

## Optionally Pass Command Line Parameters

This will allow for easier batch uploading of multiple yaml files

```bash
$ emojipacks -s <subdomain> -e <email> -p <password> -y <yaml_file>
```

## Run Batch Upload script

A file named batchUploadExample.sh is provided for your reference. Edit this file change the subdomain, email, and password parameters to your own and save it as batchUpload.sh or something similar.

This script will aid in the process of batch uploading.

It optionally takes an argument for the directory path that contains your yaml files. If this is not provided './packs' will be used by default.

```bash
$ ./batchUpload.sh [path_to_yaml_files]
```

## Emoji Yaml File

Also note that the yaml file must be indented properly and formatted as such:

```yaml
title: food
emojis:
  - name: apple
    src: http://i.imgur.com/Rw0Vlda.png
  - name: applepie
    src: http://i.imgur.com/g4RU1fM.png
```

..with the `src` pointing to an image file. According to Slack:

Note: in this fork, emojis stored in the `emojis` folder can omit the `src` propery if the `name` property matches `name.png` in the emojis folder. Use it, don't use it, up to you. The normal method of providing it in the yaml is still supported as before.

- Square images work best
- Image can't be larger than 128px in width or height
- Image must be smaller than 64K in file size

### Emoji Aliases
It is possible to give multiple names to a single emoji using yaml such as:
```yaml
title: octicons
emojis:
  - name: pr
    aliases:
      - pullrequest
      - mergerequest
    src: https://i.imgur.com/rhwNxfc.png
```

## License (MIT)

```
WWWWWW||WWWWWW
 W W W||W W W
      ||
    ( OO )__________
     /  |           \
    /o o|    MIT     \
    \___/||_||__||_|| *
         || ||  || ||
        _||_|| _||_||
       (__|__|(__|__|
```

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the 'Software'), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
