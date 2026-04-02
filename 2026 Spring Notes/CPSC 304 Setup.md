***
sh ifung01@remote.students.cs.ubc.ca

sh ./remote-start.sh
sh ./scripts/mac/server-tunnel.sh

rlwrap sqlplus ora_ifung01@stu

username: ora_ifung01@stu
password: a96027370



SET LINESIZE 200;
SET PAGESIZE 100;
COLUMN title FORMAT A20;
COLUMN courtName FORMAT A20;