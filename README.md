# test_environment
Basic test environment containing 2 gateways, a database and an SMTP server.

gateway given hostname 'gateway' can be launched on the browser using gateway.localtest.me:hostPort. This is the only way to run two gateways
on the same browser

docker exec -it contName/ID bash -> command is used to enter container's bash terminal

example: docker exec -it mariadbName bash
root@contID:/ # mysql -u username -ppassword databasename

it's a volume mapping
./gw-init/frontend.gwbk:/restore.gwbk
you map a file from a mount point on the host to a mount point in the container
It's like a copy operation. You copy file from host volume to container volume.
And then on start up
 -r /restore.gwbk
you restore from the file at the container mount point. Command to perform restore
operation using file found at specified mount point.

This looks complicated but it's a once-off copy operation.
with docker compose cp source dest command we copy from a mountpoint on the container to a mount point on the host
docker compose cp frontend:/usr/local/bin/ignition/data/.uuid ./gw-init/frontend-uuid.txt
You'll do the same for the backend gateway and copy the metro files as well
docker compose cp frontend:/usr/local/bin/ignition/data/local/metro-keystore gw-init/frontend-metro-keystore

At the end of this operation, you'll have the gwbk files, the uuids and the metro-keystores

We went through the process of copying files into a directory in the same parent folder as the compose file (i.e made files
accessible to compose file)

Now that files are accessible: first we
use the backup files to restore both gateways on start up
Now we...
when containers are created we...

docker compose down -v 
is used to stop containers and remove their volumes
sidenote: compose is to docker what EAM Controller is to EAM Agent


