docker-freelan-privileged-node
==============================

The base image for a node that is able to start IPython SSH ipcluster engines over the network


This node won't have an ssh server, it won't be receiving jobs. However the host machine can run both a privileged node and a worker node if it desires.

This node will have an initialise script which will do the following:
 
 * Uses environmental variable for location of certificate authority (ca)
 * Create certificate and send it off for signing accompanied by ca defined auto-sign network password (also environmental variable)
 * Pull the supernode repo
 * Creates the freelan config file based on the other available supernodes
 * Starts up freelan and joins the network
 * Request access to collaborate on the privaleged nodes git repo so that the github user of the node may add its VPN network ip to the privlidged nodes list

User will then save this initialised docker image locally
