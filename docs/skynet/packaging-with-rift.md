# Packaging a Skapp with Rift and deploying it to Skynet

## Let's turn your App into a Skapp!

This tutorial will show you how to use Rift to set up a resolver skylink, package your web app for Homescreen, and deploy it to Skynet.

### 1. Creating a resolver skylink

<img src="/static/assets/packaging-with-rift/3.png">

* (Optional) Log into your Skynet Portal.
This will ensure your web app will stay pinned in the future.
You can use [https://siasky.net](https://siasky.net) and sign up for a free account to pin up to 100GB worth of data.
We will be using the `siasky.net` Portal for the rest of the tutorial, but please replace `.siasky.net` in the links if you are using a different Portal.

* Visit [https://riftapp.hns.siasky.net/#/dns](https://riftapp.hns.siasky.net/#/dns).

<img src="/static/assets/packaging-with-rift/1.png">

* Make sure you are logged into your MySky account (top right button).

<img src="/static/assets/packaging-with-rift/2.png">

* Click the Add DNS Record button.

* Enter a name for your app and a skylink. This is temporary.

You can use the following skylink as a placeholder:

`RAAsjQh2n1AMdesCr9wLYa73VqmzqmgVJ75ookOGyHDiDA`

* Save.

* Take note of the **resolver skylink** you have created. It will point to the **target skylink** of your choice.

### 2. Packaging your app for Homescreen and Skynet

* Follow the instructions here to configure your Manifest file:

[https://docs.siasky.net/integrations/homescreen/adding-homescreen-support-to-an-app#3-configure-your-manifest-file](https://docs.siasky.net/integrations/homescreen/adding-homescreen-support-to-an-app#3-configure-your-manifest-file).

The skylink for the Manifest file is the **resolver skylink** you created in the previous step.

Once your Manifest file is configured, your web app is ready to be deployed.

### 3. Deploying your app to Skynet

<img src="/static/assets/packaging-with-rift/6.png">

* Visit [https://riftapp.hns.siasky.net/#/files](https://riftapp.hns.siasky.net/#/files) and select the `directory` option.

* Click on the box or drag and drop to upload the folder containing your web app. 

`Index.html` has to be present in the root of the folder.

When the upload completes, you will obtain your **target skylink**. Take note of it.

We will now point the **resolver skylink** you created in step 1 to this **target skylink**.

### 4. Updating your resolver skylink

* Go to [https://riftapp.hns.siasky.net/#/dns](https://riftapp.hns.siasky.net/#/dns) and click on the entry you created in the first step.

* Update the **target skylink** to the skylink you obtained at the end of the previous step.

* Save.

* Voilà! Your web app is now packaged and ready for Homescreen.

Now, let's make clickable media for users to easily add your app to Homescreen.

### 5. Creating clickable links and buttons

* The following link will take users directly to Homescreen and prompt them to add your application.

`https://homescreen.hns.siasky.net/#/skylink/[skylink]`

* Replace [skylink] with the **resolver skylink** you created in step 1.

* Make sure everything works and looks nice in Homescreen, so try visiting the link yourself!

* Ta-da! You can now share this link with users.

* You can also follow these instructions to make an `Add to Homescreen` button for your website or github page:

[https://docs.siasky.net/integrations/homescreen/adding-homescreen-support-to-an-app#4-add-the-homescreen-button-on-your-projects-readme](https://docs.siasky.net/integrations/homescreen/adding-homescreen-support-to-an-app#4-add-the-homescreen-button-on-your-projects-readme)

You have now packaged your web app for Homescreen and deployed it to Skynet. 

Users are now able to add your web app to Homescreen and stay up to date.

If you update your web app, simply update the target skylink in Rift.

Have fun deploying your apps to Skynet!

*Written by: Napster, Last Edit: September 21, 2021*
