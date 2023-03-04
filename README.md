Terraform module to provision an EC2 instance that is running Apache


provider = "aws"{
region = us-east-1
}

module "apache" {
  source          = ".//terraform-aws-apache-example"
  vpc_id          = "vpc-0000000000"
  my_ip_with_cidr = "MY_OWN_IP/32"
  public_key      = " ssh-rsa AAAB.......
  instance_type   = "t2.micro"
  server_name     = "Apache server"
}


output "public_ip" {
  value = module.apache.public_ip
}
