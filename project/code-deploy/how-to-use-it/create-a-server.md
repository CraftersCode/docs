# Create a server

Let's create a server first. please use `root` user.

<figure><img src="../../../.gitbook/assets/Screenshot 2024-08-12 at 20.08.34.png" alt=""><figcaption></figcaption></figure>

After creating the server, we need to adding public key to our server. if you did'nt setup the server yet, please follow this [instruction](../pre-requisite.md).



Copy the ssh public key.

<figure><img src="../../../.gitbook/assets/Screenshot 2024-08-12 at 20.12.22.png" alt=""><figcaption></figcaption></figure>

Remote your server with root user

```bash
ssh root@your.server.public.ip
```

open authorized\_keys and paste your public key

```bash
nano .ssh/authorized_keys
```

and then  `Check connection`, make sure the connection is successfully

<figure><img src="../../../.gitbook/assets/Screenshot 2024-08-12 at 20.17.18.png" alt=""><figcaption></figcaption></figure>

Congrats, your server added to CodeDeploy!
