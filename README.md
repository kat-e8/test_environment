# test_environment
Basic test environment containing 2 gateways, a database and an SMTP server.

gateway given hostname 'gateway' can be launched on the browser using gateway.localtest.me:hostPort. This is the only way to run two gateways
on the same browser

docker exec -it contName/ID bash -> command is used to enter container's bash terminal

example: docker exec -it mariadbName bash
root@contID:/ # mysql -u username -ppassword databasename
