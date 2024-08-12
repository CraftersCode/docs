# Adding site

This step i assuming you already setup your site, if you using cloudpanel follow this [instruction](https://www.cloudpanel.io/docs/v2/php/applications/laravel/) to add the site first.

Of course you can use your favorite panel too.



### Let's get started

Navigate to server list and click `Site` button.

Next step, add your site information. And then click create.

<figure><img src="../../../.gitbook/assets/Screenshot 2024-08-12 at 20.21.35.png" alt=""><figcaption></figcaption></figure>

After created, then click `Manage site.`

You will see this page

<figure><img src="../../../.gitbook/assets/Screenshot 2024-08-12 at 20.23.48.png" alt=""><figcaption></figcaption></figure>

Now lets check if the site is installed successfully, navigate to Deployment Page. And add `php artisan about` to see if it working. Then, click deploy now.

<figure><img src="../../../.gitbook/assets/Screenshot 2024-08-12 at 20.39.39.png" alt=""><figcaption></figcaption></figure>

Click `Enable Quick Deploy` If you want to activate `Push to Deploy.`&#x20;



Next step, Let's navigate to Repository page.

<figure><img src="../../../.gitbook/assets/Screenshot 2024-08-12 at 20.26.15.png" alt=""><figcaption></figcaption></figure>

| Section            | Description                                                                                                                                                                  |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Repository         | <p>If your GitHub account is connected with CodeDeploy, you will see a list of your repositories.</p><p></p><p>You can leave this empty if the account is not connected.</p> |
| Branch             | CodeDeploy uses this branch to gather details of the latest commit when you deploy your application.                                                                         |
| Site detail        | CodeDeploy uses this data to deploy your application                                                                                                                         |
| Deploy Webhook URL | You can use this URL to trigger deployments remotely, You can send a "post" request to this URL.                                                                             |





Let's change the branch to the main & generate webhook url

<figure><img src="../../../.gitbook/assets/Screenshot 2024-08-12 at 20.31.29.png" alt=""><figcaption></figcaption></figure>

Copy the webhook url, and then add it to github.

{% hint style="info" %}
You can skip this step if you did'nt enabled the Quick Deploy


{% endhint %}

<figure><img src="../../../.gitbook/assets/Screenshot 2024-08-12 at 20.37.26.png" alt=""><figcaption></figcaption></figure>

