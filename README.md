📌 Objective

Install and run Netdata to visualize system and application performance metrics in real-time using Docker.

⚙️ Tools Used

Netdata (Open-source monitoring tool)

Docker


✅ Step 1: Run Netdata Using Docker
docker run -d --name=netdata -p 19999:19999 --cap-add SYS_PTRACE --security-opt apparmor=unconfined netdata/netdata
This command:

Runs Netdata in detached mode (-d)

Names the container netdata

Maps host port 19999 to container port 19999

Grants necessary permissions for system metrics

✅ Step 2: Access Netdata Dashboard
Open your browser and go to:


http://localhost:19999
Here you can monitor:

CPU usage per core

RAM and swap memory

Disk I/O statistics

Network traffic and packet stats

Docker container metrics (if running)

Alerts, alarms, and historical charts

✅ Step 3: Access Logs Inside the Container
Enter the Netdata container shell:

docker exec -it netdata /bin/bash
Navigate to the logs directory:

cd /var/log/netdata
ls
View log files:

cat error.log      # View errors and internal issues
cat access.log     # View dashboard access logs
Exit the container:

✅ Step 4: Stop & Clean Up
Stop the running Netdata container:

docker stop netdata
Remove the container:

docker rm netdata

docker rmi netdata/netdata