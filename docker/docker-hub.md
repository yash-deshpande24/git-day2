### Step 0: Install Docker on Ubuntu

Run these commands one by one:

```bash
sudo apt update -y
sudo apt install docker.io -y
sudo systemctl start docker
sudo systemctl enable docker
sudo usermod -aG docker ubuntu
newgrp docker
sudo chmod 777 /var/run/docker.sock
```

---

### Step 1: Open Docker Hub

Go to [https://hub.docker.com](https://hub.docker.com).

### Step 2: Search for User

* In the search bar, type **`abhipraydh96`** and open the account.

### Step 3: View Repositories

* You will see all repositories created by this user.
* Example: `abhipraydh96/yoga`.

### Step 4: Pull the Repository Image

Run this command to pull an image (example tag `v2`):

```bash
docker pull abhipraydh96/yoga:v2
```

### Step 5: Verify Pulled Images

Check available images:

```bash
docker images
```

---

### Step 6: Generate a Docker Hub Token

1. Login to Docker Hub.
2. Click your **profile logo → Account Settings**.
3. Scroll down to **Security → Personal Access Tokens**.
4. Click **Generate Token**.
5. Assign policies: **Read, Write, Delete**.
6. Generate → Copy the token (save it securely).

---

### Step 7: Login to Docker Hub with Token

Run this command (replace username with your Docker Hub username):

```bash
docker login -u deshpandeyashrajesh -p <your_generated_token>
```

---

### Step 8: Retag the Pulled Image

Tag the pulled image to your own account namespace:

```bash
docker tag abhipraydh96/yoga:v2 deshpandeyashrajesh/yoga:v2
```

---

### Step 9: Push Image to Your Account

Push the image to your Docker Hub repository:

```bash
docker push deshpandeyashrajesh/yoga:v2
```

---

### Step 10: Confirm on Docker Hub

* Go to your Docker Hub account (`deshpandeyashrajesh`).
* You should see a repository **`yoga`** with the tag `v2` successfully pushed.
