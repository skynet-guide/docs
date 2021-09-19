# Packaging a Skapp with Rift

This tutorial will show you how to package your web application for Homescreen.
We will set up a resolver skylink with your MySky account, package your web app, and upload it to Skynet.

### 1. Creating a temporary resolver skylink

* Visit [https://siasky.net](https://siasky.net)
Make sure you have an account on Siasky.net and that you are logged in. This will ensure your web app will stay pinned in the future.

<img src="/static/assets/packaging-with-rift/3.png">

* Visit [https://riftapp.hns.siasky.net/#/dns](https://riftapp.hns.siasky.net/#/dns)
Make sure you are logged in (top right button).

<img src="/static/assets/packaging-with-rift/1.png">

* Click the Add DNS Record button.

<img src="/static/assets/packaging-with-rift/2.png">

* Enter a name for your app and a skylink. This is temporary. You can use this image as a placeholder: `0005u6fn0vr814bu7oo45knno9cuesi1r58mebstineid7giin75t38`
Hit Save.

* Take note of the **resolver skylink** you have now created.

### 2. Packaging your app for Homescreen and Skynet

* Follow the instruction here to configure your Manifest file:
[https://docs.siasky.net/integrations/homescreen/adding-homescreen-support-to-an-app#3-configure-your-manifest-file](https://docs.siasky.net/integrations/homescreen/adding-homescreen-support-to-an-app#3-configure-your-manifest-file)

Your skylink here is the **resolver skylink** you created in the previous step.
Once your Manifest file is configured, your web app is ready to be deployed.

### 3. Upload your app to Skynet

* Visit [https://siasky.net](https://siasky.net) and click "Do you want to upload a web app or directory?"

<img src="/static/assets/packaging-with-rift/4.png">

* Upload the folder containing your web app (index.html has to be present in the root).
The UI will output a link for you. Great! However, this link is not in the right format. We will now retrieve the skylink in the format we need.

* Click on My Account in the top right.

<img src="/static/assets/packaging-with-rift/3.png">

* View all Uploads.

<img src="/static/assets/packaging-with-rift/5.png">

* Locate your web app. This has the skylink we need. Take note of it.

### 4. Update your resolver skylink

* Go to [https://riftapp.hns.siasky.net/#/dns](https://riftapp.hns.siasky.net/#/dns) and click on the entry you created in the first step

* Update the target skylink to the skylink you obtained at the end of the previous step.
Save.

* Voilà! Your web app is now packaged and ready for Homescreen.
Now, let's make a clickable link for users to easily add your app on Homescreen.

### 5 Create a clickable link

* The following link will take users directly to Homescreen and prompt them to add your application.

`https://homescreen.hns.siasky.net/#/skylink/[skylink]`

Replace [skylink] with the **resolver skylink** you created in step 1.
Make sure everything works and looks nice in Homescreen, so try visiting the link yourself!

Ta-da! You can now share this link with users.

You can also follow these instructions to make an `Add to Homescreen` button for your website or github page:
[https://docs.siasky.net/integrations/homescreen/adding-homescreen-support-to-an-app#4-add-the-homescreen-button-on-your-projects-readme](https://docs.siasky.net/integrations/homescreen/adding-homescreen-support-to-an-app#4-add-the-homescreen-button-on-your-projects-readme)

You have now packaged your web app for Homescreen and deployed it to Skynet. 
If you update your web app, simply update the target skylink in Rift.
Users will now be able to add your web app to Homescreen and stay up to date.

*Written by: Napster, Last Edit: September 19, 2021*
