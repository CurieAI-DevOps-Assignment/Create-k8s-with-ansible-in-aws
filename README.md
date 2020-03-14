# Create-k8s-with-ansible-in-aws

#prerequasites
1)one s3 bucket i,e. bharathk8s.k8s
2)one private hosted zone i,e. bharathk8s.k8s
3)one ec2 instance with s3,ec2,route53 full access policys 


#procedure
1)run ssh.yml playbook(above) using ansible.
2)run k8s.yml playbook(above) using ansible.
3) run fallowing command on kops server

#kops create cluster --name=bharathk8s.k8s --state=s3://bharathk8s.k8s --zones=us-east-1 --node-count=1 --master-size=t2.micro --node-size=t2.micro --dns-zone=bharathk8s.k8s --dns private

#kops update cluster bharathk8s.k8s --yes --state=s3://bharathk8s.k8s

4)your cluster is ready.

5)dalete cluster command
kops delete cluster --name bharathk8s.k8s --state=s3://bharathk8s.k8s --yes
