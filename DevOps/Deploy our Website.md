- - -
![[Pasted image 20240629200000.png|600]]

- - -
## React(pure frontend Or which do not use SSR)

- Websites doesn't understand .jsx or .tsx files. We have to convert this to only .js , .html and .css files.
- We can do this by running  build command ```npm run build```.
- When we run this , a new folder is generated called 'dist'. This is what we distribute OR deploy on the Internet.
![[Pasted image 20240629200300.png|300]]

### Vercel ->
It is a PaaS. Often quite expensive.

### Virtual Machines ->
We can rent VM from EC2 Servers in AWS. It is not scalable beyond a Certain point. Plus we are just serving static files , so we don't actually need VMs. 

### CDNs and Object Stores ->
![[Pasted image 20240629204623.png|600]]

- We request static files(files that same for everyone) like static site like blog, social medias , streaming... through Content Delivery Networks from either EC2 or Object Stores.
- A content delivery network (CDN) is ==a network of servers that are geographically distributed to speed up the delivery of web content to users==. When a user visits a website, data from the website's server has to travel across the internet to reach the user's computer. If the user is far from the server, it can take a long time to load large files like images or videos. 
- CDNs store cached content on edge servers that are closer to the user, which minimizes latency and allows for faster transfer of assets needed to load content.

## When should we use CDN+Object Store ?
- Serving Videos.
- jpeg ,jpg images.
- Static website not using SSR.

CDN -> Cloudfront                             Object Store -> AWS S3
Alternate --> bunny

### STEPS ->
1. Sign Up.
2. Create an Object Store.
3. Create a CDN.
4. Connect the CDN to the Object Store.
5. Connect domain to CDN.

![[Pasted image 20240630002648.png|800]]

- - -

## NodeJS/NextJS/Scaling of Backend

Every request needs to directly go the Server/EC2 or any backend. You can't use CDNs as you can not Cache data cause every user will have unique set of datas.

