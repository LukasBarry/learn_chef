# Building Servers with Chef

## Chef Commands to build server

1. Create directory in current working directory for Chef
2. If you plan on using a local text editor, take note of the name of your new directory

#### Start Container
`docker run -it -v $(pwd):/root/chef-repo -p 8100:80 ubuntu:14.04 /bin/bash`
    - if you are using local text editor, replace `chef-repo` with the name of your working directory
    
Then run:
`apt-get update`
`apt-get install curl -y`
and finally, to install the Chef DK:
`curl https://omnitruck.chef.io/install.sh | bash -s -- -P chefdk -c stable -v 2.3.4`

### Run recipe locally
`chef-client --local-mode fil_name.rb`
    - replace `file_name` with the file name
    - runs receipe in local mode
    
### Start server
`curl localhost`
    - after running this command, you can go to `localhost:8100` and verify that your webpage is working
