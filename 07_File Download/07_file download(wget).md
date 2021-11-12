# file download

If you want to download files in Linux, we use program named __wget__. Now we are going to learn about how to use it.

### wget

Basically to use _wget_, just enter _wget (file url)_. Now files are downloaded, but download file name is not so good at verifying file...=(
```r
mhj@mhj-ideapad:~$ wget https://images.app.goo.gl/QESGcXBbakQixmsFA
...
(670 KB/s) - ¡®QESGcXBbakQixmsFA¡¯ saved [30880]
```
file name is 'QESGcXBbakQixmsFA', but it is very bad file name beacuse we can't know about this file before we open it. 

### wget -O (file name)

 So we use __-O__ to name files before download it. 
 ```r
 mhj@mhj-ideapad:~$ wget -O black_backgroundImg https://images.app.goo.gl/QESGcXBbakQixmsFA
...
(616 KB/s) - ¡®black_backgroundImg¡¯ saved [30838]
```

Now we can change file name before download it. It is much better than before!!