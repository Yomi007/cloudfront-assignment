# How to host a static webpage on a private AWS S3 BUCKET and accessing its content using CLOUDFRONT

Here , i am going to breaking down the steps of how to host a static webpage on a private AWS S3 BUCKET and accessing its content using CLOUDFRONT. 

You probably must be thinking, What is cloud front?. 
Cloud front is a content delivery system provided by AWS which helps to deliver your websites, applications or other internet content to users with low latency and high transfer speed, in more relatable terms.

Imagine CloudFront as a network of post offices strategically located around the world (edge locations). When someone orders something from your online store (origin server), the closest post office (edge location) checks if it already has the item in stock (cached content). If it does, it delivers it quickly (reduced latency). If not, the post office retrieves it from your main warehouse (origin server) and stores it locally for future orders. This network of post offices helps deliver your products (website content) faster to customers (users) around the world.

Now that we know what CLOUDFRONT is, lets go ahead and get our hands dirty.




### First, We search for s3 bucket in the search bar, click on s3 to create a s3 bucket


<img width="943" alt="image" src="https://github.com/Yomi007/cloudfront-assignment/assets/40344655/ef492317-7921-415c-b19b-aa40d7c600cb">


### Next, you click on create bucket

<img width="873" alt="image" src="https://github.com/Yomi007/cloudfront-assignment/assets/40344655/5d305399-9a6b-45cf-8f27-c7767f44d1e4">

### Give your bucket a name under bucket name and ensure it is unique

<img width="880" alt="image" src="https://github.com/Yomi007/cloudfront-assignment/assets/40344655/8651e6d7-4a13-41d7-a77f-245aa21dee93">

### Leave all other settings for now, scroll down and click on create bucket, it takes a couple of seconds to create and you should wait it out.

<img width="893" alt="image" src="https://github.com/Yomi007/cloudfront-assignment/assets/40344655/f9889a7c-a83e-4e07-898c-1cc868a15e7e">

### You should see your bucket as it is in the screenshot below. Click on the name of the bucket eg. mine is Yomi007 in the screenshot.

<img width="901" alt="image" src="https://github.com/Yomi007/cloudfront-assignment/assets/40344655/e197928c-2ce6-4a13-9ecd-a873bb451ce1">

### You should see this. Click on upload

<img width="948" alt="image" src="https://github.com/Yomi007/cloudfront-assignment/assets/40344655/2493ef4f-24ba-49e9-b25d-7a9e6d0be9e4">

### Then click on add files, the select the files of your website that you want to add on your local computer.

<img width="938" alt="image" src="https://github.com/Yomi007/cloudfront-assignment/assets/40344655/e942f905-3528-40bc-a89f-e1399e3f8970">

## do the same for folders to also add folders of your website.

<img width="922" alt="image" src="https://github.com/Yomi007/cloudfront-assignment/assets/40344655/c3487aed-2eea-4163-9e16-ff7fb933e70b">

## Type CLOUDFRONT in the search bar and you should see the following, then click on cloud front.

<img width="947" alt="image" src="https://github.com/Yomi007/cloudfront-assignment/assets/40344655/c08066fa-f9cb-4507-8d36-59093160640f">


## click on upload, It takes a little while so we would wait it out, once we are done with uploading, we move over to CLOUDFRONT.

<img width="883" alt="image" src="https://github.com/Yomi007/cloudfront-assignment/assets/40344655/d4bd36ee-4291-493a-95b5-4654eca117ba">

## After searching for cloudfront and clicking on it, you should see this. Go alead and select create distribution

<img width="951" alt="image" src="https://github.com/Yomi007/cloudfront-assignment/assets/40344655/33042dd3-93f7-4dea-be7f-1719f771a7ff">

## Click on origin domain and a dropdown will apprear, select the s3 bucket that you created previously.

![image](https://github.com/Yomi007/cloudfront-assignment/assets/40344655/de82d4d4-b641-4c91-b6e1-7757de642df8)

## scroll down and under origin access, click on origin access control settings and the below should appear, click on create new oac.

<img width="887" alt="image" src="https://github.com/Yomi007/cloudfront-assignment/assets/40344655/4adcce40-e4ea-436b-9052-3ca4fc1363dc">

## Dont change anything and click on create

<img width="464" alt="image" src="https://github.com/Yomi007/cloudfront-assignment/assets/40344655/8a763a27-fdff-4c61-b7be-5e0d48cc916c">

## Scroll down to default root object and type in "index.html" and click on create

<img width="814" alt="image" src="https://github.com/Yomi007/cloudfront-assignment/assets/40344655/b9b5cb91-6341-40d1-91c5-7fd217ed5949">

## click on copy policy and ensure it is copied. Then, click on go to s3 bucket to update policy to take you back to the s3 bucket

<img width="923" alt="image" src="https://github.com/Yomi007/cloudfront-assignment/assets/40344655/b294fb03-4e0f-4c3e-9ca2-8c6ea67a04a8">

## Click on permission tab and scroll down to bucket policy.

<img width="949" alt="image" src="https://github.com/Yomi007/cloudfront-assignment/assets/40344655/3cad7611-cfe7-44a5-931f-d571bc1aa8cf">

## Upon getting to bucket policy, click on edit , paste the policy which are few lines of codes and click on save changes

<img width="933" alt="image" src="https://github.com/Yomi007/cloudfront-assignment/assets/40344655/f4f7e6d9-a7e2-4c65-aeb3-563a33818c33">

## click on the properties tab, when you get to static webhosting, click on edit. There are two things you will change. First, enable static webhosting
## secondly under index document, input the default page of the website which is generally "index.html.

<img width="947" alt="image" src="https://github.com/Yomi007/cloudfront-assignment/assets/40344655/cd0ffb7b-016f-4c58-b307-19363687ed9d">

<img width="695" alt="image" src="https://github.com/Yomi007/cloudfront-assignment/assets/40344655/2ea89033-447e-48ad-947c-ea97ac09a5b9">

<img width="896" alt="image" src="https://github.com/Yomi007/cloudfront-assignment/assets/40344655/fc0fa2eb-fdad-4b66-b2a7-52e795853e27">

## Finally , lets go back to out cloud front, copy distribution domain name, paste it in our browser and it should be able to display our website.

<img width="944" alt="image" src="https://github.com/Yomi007/cloudfront-assignment/assets/40344655/a7f9c58b-0223-4593-b33e-32871ab31e68">

![image](https://github.com/Yomi007/cloudfront-assignment/assets/40344655/cef130a1-17bd-42be-9857-d8b26d21b01b)

## There we go, we have successfully hosted a static webpage on a private AWS S3 BUCKET and accessing its content using CLOUDFRONT.


