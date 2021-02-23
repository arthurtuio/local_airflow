# How to install and run airflow on an EC2 #

**Make sure to get an big EC2 instance, like t2.medium, as the free tier won't be able to get the job done**

1. Create an EC2 Instance, leaving open at least the port 8080 for HTTP requests
2. Log in your AWS profile using `export AWS_PROFILE=<your_profile>`
3. Run `chmod 400 mykey.pem`
4. ssh into the instance: `ssh -i mykey.pem ec2-user@my-instance-public-dns-name`
5. In the instance, go root level (sudo su), install git and pip:
  ```
  yum install git-all
  yum install python3-pip
  ```
6. Clone this repo
7. **If the EC2 doesnt have apt**, then run:
  ```
  yum install python-devel mysql-devel
  yum install gcc python3-devel
  ```
8. Install the requirements
9. Initialize the airflow db, webserver, configs, etc. **Follow this link: https://medium.com/@abraham.pabbathi/airflow-on-aws-ec2-instance-with-ubuntu-aff8d3206171**

10. Another link that might help is this: https://christo-lagali.medium.com/getting-airflow-up-and-running-on-an-ec2-instance-ae4f3a69441
  -> Here it shows which folder is airflow.cfg and how to change the port  (`nano airflow.cfg`, `ctrl+O` to save and `ctrl+X` to quit)

11. Acredito ser necessario criar um banco de dados pra rodar o airflow, esse tutorial aqui ensina como criar um postgres https://www.hostinger.com.br/tutoriais/postgresql-centos-7
