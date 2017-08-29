# AWS Project Task

Task for AWS project

### Create nexus image

```bash
ansible-playbook -i ec2.py create_nexus_image.yaml --private-key=<path_to_key> --extra-vars "ami_id=<base_image(e.g ami-cfdafaaa)> aws_region=us-east-2 aws_zone=us-east-2a key_name=<keyname> (ec2_tag_Name=<sometags>)"
```

### Start private nexus stack
```bash
ansible-playbook start_nexus_stack.yaml --extra-vars "stack_name=<stack_name> aws_region=us-east-2"
```
### Start public nexus stack

```bash
ansible-playbook start_nexus_stack.yaml --extra-vars "stack_name=<stack_name> aws_region=us-east-2 private=false"
```

Full list of extra vars with defaults:

- key_name: "vburak"
- instance_type: "t2.medium"
- image_id: "ami-15cbe870"
- customer_vpn_addr: "11.11.11.11" (works with private=true only)
- customer_vpn_cidr: "172.16.0.0/16" (works with private=true only)
- private: true

