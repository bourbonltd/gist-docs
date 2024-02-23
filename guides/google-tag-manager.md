---
description: Setup Gist for Web in under 10 minutes.
---

# Google Tag Manager

Integrating Gist using Google Tag Manager is very easy and can be done in just a few minutes.

Open your GTM account page and select **New Tag**

![](<../.gitbook/assets/image (9).png>)

Name the tag **Gist**, this is located on the top left of the new page**.**

![](<../.gitbook/assets/image (4).png>)

Click on **Tag Configuration**, and select **Custom HTML**

![](<../.gitbook/assets/image (6).png>)

Paste in the following code snippet and change the organization id to match yours. Your organization id can be copied from [here](https://app.gist.build/integration).

```markup
<script src="https://code.gist.build/web/stable/gist.min.js"></script>
<script>
  Gist.setup(
    { 
      organizationId: "organization-id-here",
      useGuestSession: true
    }
  );
  Gist.subscribeToTopic("announcements");
</script>
```

![](<../.gitbook/assets/image (1).png>)

Click on the **Triggering** section and select **All pages.**

Click **Save**

To preview your changes select **Preview**

![](<../.gitbook/assets/image (7).png>)

Input the URL of your website and click **Start**

![](<../.gitbook/assets/image (5).png>)

Back on **Gist**, go to [**Broadcasts**](https://app.gist.build/broadcasts) and select **Create Broadcast**

![](<../.gitbook/assets/image (17).png>)

Create a test broadcast, choose a name, message, add **announcements** as a topic and pick a **start date in the past** and an **end date in the future**.

![](<../.gitbook/assets/image (10).png>)

Click **Save** and then **Publish**

Your announcement should appear on your preview site.

![](<../.gitbook/assets/image (14).png>)

Before you publish the changes to GTM make sure you go back to Gist and **unpublish** the test broadcast.

Now, back at Google Tag Manager, click **Submit**

![](<../.gitbook/assets/image (8).png>)

Provide a version name and description and click **Publish**.

![](<../.gitbook/assets/image (15).png>)

That's it! Gist is now setup on your web product. You can now broadcast messages to anyone visiting your site by adding the **announcements** topic.

For more details on how to further integrate Gist into your product, you can have a look at our official web library [documentation](../libraries/web.md).
