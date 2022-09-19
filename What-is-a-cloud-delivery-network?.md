# What is a Cloud Delivery Network (CDN)?

## What is the problem at hand?

Say our website, including assets (images, videos, etc...) are hosted on a server in Montreal, Quebec. Bob is trying to access our website from Dallas, Texas (~2,800 KM away) and Alice is trying to access our website from Ottawa, Ontario (~187 KM away). Alice will experience a much smaller wait time (granted in milliseconds) than Bob will when accessing our site. This is where a Content Delivery Network (CDN) comes in.

## What is a Content  Delivery Network (CDN)?

A content delivery network (usually)  shortens the amount of time it takes for a user to access an applications asset.

## How does a Content Delivery Network (CDN) work?

A content delivery network is a series of servers which are placed in various locations to act as access points for users when delivering content. By uploading our content to multiple servers (access points) around multiple regions we are shortening the distance and therefore the time (although distance is not the only factor) it takes for our content to reach the user. As a result of this, the access points have reduced  the load of traffic from the main server, not only protecting it (security through obscurity), but can also result in even quicker response times for those closest to the main server.

## What is our Content Delivery Network?

Currently, we use Amazon Web Services (AWS) for all out CDN needs. We have a S3 bucket (storage bucket) which stores our content, and we use Amazons CloudFront service in order to deploy our content to their CDN. We can then access the CDN via simple  URL  as such  https://\<distribution-domain-name>/<asset-name.asset-extension>
