Skip to the content
products
Team
enterprise
To explore
Marketplace
prices
To search for
Log in
Sign up
deeplearningzeroall
/
PyTorch
Public
Code
Problems
14
pull requests
3
Actions
projects
Week
Safety
perceptions
PyTorch/docker_user_guide.md
@mgh3326
mgh3326 update 'pip update'
Last commit 0c5ab31 on 19 Jul 2019
 History
 2 collaborators
@simonjisu@mgh3326
144 lines (87 sloc) 5.11 KB

Docker User Guide
This is how you use Docker written for Docker users.

Docker Installation Guide
Docker Introduction and Guide - Sang-Jun Oh

Instructions after installing Docker
Running Docker for the first time
After running Docker Terminal, memorize the IP from the image below!

We will use this IP to communicate with the Docker container in the future.

Image

Download docker image
Get the docker image from hub.docker and prepare the container for use. (Sign-in may be required. Sign up at https://hub.docker.com!)

$ docker pull deeplearningzerotoall/pytorch
If you want to specify a different version, connect to our docker hub and check the version you want.

After receiving the image, run the command to verify the existence of the Docker image docker images.

$ docker images
REPOSITORY TAG ...
hello-world latest ...
deeplearningzerotoall/pytorch latest ...
Running docker image containers and shutting them down
Create and run a container from a docker image. At this --name point, you can set any name you like. In this guide, we

$ docker run -i -t --name en -p 8888:8888 -p 8097:8097 deeplearningzerotoall/pytorch /bin/bash
We are almost there. You created a docker container and connected to the container's internal shell with the root account.

root@[고유번호]:~#
If you want to completely shut down the container, exit, just type the command!

root@[고유번호]:~# exit
docker ps -aYou can use the command to check if your Docker container is currently running. Check STATUS

$ docker ps -a
Docker container moves freely
Note: docker runYou only need to run the command once. To run the terminated container again, run as follows.

$ docker start en
This step only made the container grow. Run the following to connect to the container terminal. This will take you to a terminal inside the container.

$ docker attach en
root@[고유번호]:~#
If you want to leave the container on and exit for a bit, use Ctrl+P+ Ctrl+Q. Likewise, you can use the command to reconnect docker attach.

Fork and Git Clone to study
Now, to start studying for real, go to Deep Learning Github for Everyone.

ForkLog in to your Github account and click the button in the top right corner as shown in the image below.

Image

ForkOnce done, go to your repositories (after clicking your profile picture in the top right, Your repositories), a forked repository is created from this github.

Image

Click on the relevant repository to access it Clone or download and press the green button to copy or memorize the link below.

Image

Go back inside the Docker container again git clone and paste or type the copied link along with the command.

root@[고유번호]:~# git clone https://github.com/[github계정이름]/PyTorch.git
When finished, now go to the PyTorch directory.

root@[고유번호]:~# cd PyTorch
root@[고유번호]:~/PyTorch#
Install the necessary packages.

root@[고유번호]:~/PyTorch# pip install --upgrade pip
root@[고유번호]:~/PyTorch# pip install -r requirements.txt
We are almost there. jupyter notebookJust run it now.

root@[고유번호]:~/PyTorch# jupyter notebook --ip 0.0.0.0 --allow-root
For those who bother typing the above command every time, I've turned it into a shell script.

root@[고유번호]:~/PyTorch# sh run_jupyter_docker.sh
jupyter notebookAfter running for the first time, a long token is created in the docker terminal as shown in the image below. Copy the token.

Image

Now, in the Internet window, type ' using the IP address provided when running Docker for the first time [IP주소]:8888. The screen below will then appear.

Image

Enter the token you copied earlier. If this is your first time running it, you can also set a password. It is recommended to configure it as you only need to enter the password the next time you connect.

jupyter notebookTo exit, return Ctrl+ca the Docker terminal and press twice to exit.

All guides are now complete. I hope you study hard! :)

© 2022 GitHub, Inc.
Terms
Privacy
Safety
Status
Documents
Contact GitHub
prices
API
Training
blog
About
