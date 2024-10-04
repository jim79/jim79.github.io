---
permalink: /lcd-lab/
layout: single
---

### steps for ROS installation using WSL2
1. install WSL2 on your Windows laptop as mentioned in the above blog. 
2. Once WSL2 is installed search in the microsoft store for 'Ubuntu 20.04.6 LTS' and install it (this would take some time as a large file download would have to be done)
3. You can skip GUI forwarding as WSL2 now comes with it builtin. https://jack.kawell.us/posts/ros-windows-wsl2/#setting-up-gui-forwarding (just skip this section)
4. Now launch ubuntu from the windows start menu. The ubuntu terminal will be launched.
5. update the ubuntu OS
sudo apt-get update
sudo apt-get dist-upgrade
