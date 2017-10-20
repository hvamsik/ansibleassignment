# ansibleassignment

Ansible Assignment:

1.	Write adhoc command for 
	a.	move file from control machine to remote machine.
		Solution: 
		ansible hostname.domain.com -m copy -a "src=/etc/nginx/nginx.conf dest=/tmp/nginx/nginx.conf" --private-key=~/.ssh/keys/id_rsa -u ssh_user
		ansible localhost ansible_connection=local -m file -a "path=/etc/nginx/nginx.conf state=absent"


	b.	Stop and start the services
		Solution: 
		ansible hostname.domain.com -m service -a "name=httpd state=stopped" --private-key=~/.ssh/keys/id_rsa -u ssh_user
		ansible hostname.domain.com -m service -a "name=httpd state=started" --private-key=~/.ssh/keys/id_rsa -u ssh_user


	c.	check the disk spaces.
		Solution: 
		ansible hostname.domain.com -m command -a "df -h" --private-key=~/.ssh/keys/id_rsa -u ssh_user

2.	Write a playbook for install the niginx server and its dependences, make sure to apply the optimized way and best practices.
	Solution: Refer to the nginx playbook in the current directory
		
3.	Write a playbook to install the rabbitmq and its relevant configurations in the recommended order.
	Solution: Refer to the rabbitmq playbook in the current directory
		
4.	How Do I Copy Files Recursively Onto A Target Host? 
	Solution: 	
	programtical usage:
	- name: copying the /opt/jars/ dir to remote /opt/lib/
	  copy:
	    src: /opt/jars/'
	    dest: '/opt/lib/'
	    directory_mode: true
	  

	Print the defined environment variables from target host.
	Solution: 
	programatical usage: {{ ansible_env.VARIABLE_NAME }}
		
5.	What is the command to see Inventory Vars Defined For My Host?
	Solution: 
	ansible -m debug -a "var=hostvars['hostname']" localhost
		
6.	Can you create a custom role and how to use it in a playbook, Explain with sample code.
	Solution: Refer the nginx role in the current directory

