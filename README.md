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