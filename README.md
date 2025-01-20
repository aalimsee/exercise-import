# exercise-import

# =================
aaronlim@MacBookAir exercise-import % terraform init
aaronlim@MacBookAir exercise-import % terraform import aws_instance.example i-0217402d6ff1d553e  
aaronlim@MacBookAir exercise-import % terraform show 

aaronlim@MacBookAir exercise-import % 
aaronlim@MacBookAir exercise-import % terraform init
Initializing the backend...
Initializing provider plugins...
- Reusing previous version of hashicorp/aws from the dependency lock file
- Using previously-installed hashicorp/aws v5.84.0

Terraform has been successfully initialized!

You may now begin working with Terraform. Try running "terraform plan" to see
any changes that are required for your infrastructure. All Terraform commands
should now work.

If you ever set or change modules or backend configuration for Terraform,
rerun this command to reinitialize your working directory. If you forget, other
commands will detect it and remind you to do so if necessary.
aaronlim@MacBookAir exercise-import % terraform import aws_instance.example i-0217402d6ff1d553e
aws_instance.example: Importing from ID "i-0217402d6ff1d553e"...
aws_instance.example: Import prepared!
  Prepared aws_instance for import
╷
│ Error: Resource already managed by Terraform
│ 
│ Terraform is already managing a remote object for aws_instance.example. To import to this address you must first
│ remove the existing object from the state.
╵

aaronlim@MacBookAir exercise-import % terraform show                                           
# aws_instance.example:
resource "aws_instance" "example" {
    ami                                  = "ami-05576a079321f21f8"
    arn                                  = "arn:aws:ec2:us-east-1:255945442255:instance/i-09127d7c1c03e4364"
    associate_public_ip_address          = false
    availability_zone                    = "us-east-1b"
    cpu_core_count                       = 1
    cpu_threads_per_core                 = 1
    disable_api_stop                     = false
    disable_api_termination              = false
    ebs_optimized                        = false
    get_password_data                    = false
    hibernation                          = false
    host_id                              = null
    iam_instance_profile                 = null
    id                                   = "i-09127d7c1c03e4364"
    instance_initiated_shutdown_behavior = "stop"
    instance_lifecycle                   = null
    instance_state                       = "running"
    instance_type                        = "t2.micro"
    ipv6_address_count                   = 0
    ipv6_addresses                       = []
    key_name                             = "aalimsee-keypair"
    monitoring                           = false
    outpost_arn                          = null
    password_data                        = null
    placement_group                      = null
    placement_partition_number           = 0
    primary_network_interface_id         = "eni-0c784138448d56b8d"
    private_dns                          = "ip-10-0-5-166.ec2.internal"
    private_ip                           = "10.0.5.166"
    public_dns                           = null
    public_ip                            = null
    secondary_private_ips                = []
    security_groups                      = []
    source_dest_check                    = true
    spot_instance_request_id             = null
    subnet_id                            = "subnet-0ba45fb546723262c"
    tags                                 = {
        "CreatedBy" = "Managed by Terraform - Aaron"
        "Name"      = "aalimsee-tf-db-asg"
    }
    tags_all                             = {
        "CreatedBy" = "Managed by Terraform - Aaron"
        "Name"      = "aalimsee-tf-db-asg"
    }
    tenancy                              = "default"
    user_data                            = "fbe8170a67e166a829b4e2cc6d705e293faa9c9b"
    vpc_security_group_ids               = [
        "sg-0b6c872e819d448ae",
    ]

    capacity_reservation_specification {
        capacity_reservation_preference = "open"
    }

    cpu_options {
        amd_sev_snp      = null
        core_count       = 1
        threads_per_core = 1
    }

    credit_specification {
        cpu_credits = "standard"
    }

    enclave_options {
        enabled = false
    }

    launch_template {
        id      = "lt-0853e8fc3f45b3a7a"
        name    = "aalimsee-tf-db-launch-template"
        version = "1"
    }

    maintenance_options {
        auto_recovery = "default"
    }

    metadata_options {
        http_endpoint               = "enabled"
        http_protocol_ipv6          = "disabled"
        http_put_response_hop_limit = 2
        http_tokens                 = "required"
        instance_metadata_tags      = "disabled"
    }

    private_dns_name_options {
        enable_resource_name_dns_a_record    = false
        enable_resource_name_dns_aaaa_record = false
        hostname_type                        = "ip-name"
    }

    root_block_device {
        delete_on_termination = true
        device_name           = "/dev/xvda"
        encrypted             = false
        iops                  = 3000
        kms_key_id            = null
        tags                  = {}
        tags_all              = {}
        throughput            = 125
        volume_id             = "vol-0284f38eb01357ad0"
        volume_size           = 8
        volume_type           = "gp3"
    }
}
aaronlim@MacBookAir exercise-import % 