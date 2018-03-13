# Create CDN - Labs
* First it was created a new bucket, located in Sydney, in order to be a far region, and he uploaded an image with public access to it.
* Straight after you created that, the link for the object would take a time to load.

* Go to CloudFront - it will show 2 different delivery methods, web (for static and dynamic files to be delivered with http and https) and RTMP is for streaming media and objects, it uses Adobe media protocol RTMP.

* Create a web distribution

## Setup
* You will chose the origin of it, which could be an S3, ELB or OnPrem. You can also restrict access for your bucket files, so no one can use it for the direct link anymore, just from CloudFront.

* Select parameters like HTTP or HTTPS, allow methods GET and POST, define TTL in seconds (deafult is 24h), but it depends on your architecure, if your files use to change many times a day, you may consider changing the TTL.

* You can restrict access to contents using Restrict Viewer Access flag, with pre signed URls (url generated automatically) or pre signed Cookies.

* It can take a lot of time to provision, like half an hour.

* You can set Geo-Restrictions, which is basically defining whitelist or blacklist to which coutries can access your content.
* In `Invalidations` tab you can clear a cache for some object.

* now in your S3 you will already making use of it, you can access your files and change the domain to use CF link. and they will load with CloudFoundry.



