# Hetzner Cloud Complete Course by MJTechGuy

In this series you will learn how to setup and use Hetzner Cloud, and manage resources using the `hcloud` CLI and Terraform.

---

## Getting started.

1. Star this repo. :wink:
2. Have the following available
  - Email account
  - Credit card (for signing up with Hetzner)
  - Authy MFA app (or similar) for configuring multi-factor authentication
  - Computer with `ssh-keygen` for generating an access key

---

## About Hetzner Cloud

Website: [https://hetzner.com*](https://hetzner.cloud/?ref=JRGtolHM4Qdb)

Hetzner Cloud is an affordable cloud hosting provider with datacenters in the Europe, and East and West US.

It provides server nodes, firewalls, load balancers, generous traffic (20TB per node) and other features that are perfect for development and some production workloads.

Hetzner is **much** cheaper for the equivalent CPU and memory you get on other providers like DigitalOcean, AWS, etc. 

However, Hetzner does not (as of December 2022) have managed databases, managed Kubernetes services and other services like many of the cloud providers have. So chose your cloud provider(s) based on your needs.

Here is a pricing example comparing a 2vCPU and 2GB AMD/Intel Node running Linux on Hetzner, DigitalOcean, AWS, Azure and GCP.

- Hetzner: `cpx11` - ~$4/month
- DigitalOcean: `s-2vcpu-2gb` - $18/month
- AWS: `t3a.small` - ~$14/month (not including traffic or storage)
- Azure: Azure doesn't have a 2vCPU/2GB option, but their `B1ms` node with 1vCPU/2GB is ~$15/month not including traffic and persistent storage.
- GCP: `e2-standard-2` - ~$14/month (not including traffic and storage)

---

## Hetzner Cloud Account Setup

1. Visit [hetzner.com*](https://hetzner.cloud/?ref=JRGtolHM4Qdb) and sign up.
2. Enable Multi Factor Authentication (2FA) on your account. I recommend using [Authy](https://authy.com/) to store MFA as it allows for multiple devices and backups. 
- Click the "person" icon in the top right and select "User Account"
- Under "Settings" on the left menu, click "Two-factor authentication". 
- Click "Add new authentication method" and select "Mobile Device". 
- Scan the QR code with your mobile device using Authy (or similar app) and fill in "Description", your "Account Password" and the One Time Password (OTP) shown in the Authy app after you scanned the QR code.
- Click "+Add" and now your account is protected with multi-factor authentication

`*` This is a referral link. When you use it, you will get $20 in free credit on Hetzner and it helps me out when you use my link. Thanks!

---

## Working with Hetzner Cloud

This section covers some of the basics of working with the Hetzner Cloud Web UI to perform certain tasks.

### Create an API Key

### Add an SSH-Key

### Create Firewall

### Add Private Networks

### Create an Instance

### Snapshot an instance

### Delete an instance

---

## Managing Hetzner Cloud resources with the `hcloud` cli

1. Install the Hetzner CLI: https://github.com/hetznercloud/cli
2. Add your account using the API key you generated earlier by typing `hcloud context create some-nickname`, replacing `some-nickname` with what you want to call the account. You will be prompted for your API key.
3. Run some of the following commands to begin using the `hcloud` cli or watch the [video](https://www.youtube.com/@mjtechguy) for more information.

### Some Hetzner CLI Basic Commands

Here are some basic commands you can use to configure resources in Hetzner Cloud using the Hetzner CLI. If you need to know how to use the `hcloud` commands, you can just add `--help` to any command to see the options.

- `hcloud --help`
- `hcloud image list`
- `hcloud image list --type system`
- `hcloud server`
- `hcloud server list`
- `hcloud ssh-key list`
- `ssh-keygen -t rsa -b 4096 -f ~/.ssh/hetzner-test-key`
- `hcloud ssh-key create --name hetzner-test-key --public-key-from-file ~/.ssh/hetzner-test-key.pub`
- `hcloud server create --location ash --type cpx21 --image - ubuntu-20.04 --ssh-key hetzner-test-key --name ubutest1`
- `hcloud server create-image --type snapshot $INSTANCEID`
- `hcloud server delete $INSTANCEID`
- `hcloud ssh-key delete`

---

## Managing Hetzner Cloud resources with Terraform

1. Install [Terraform](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli) on your platform of choice. 
2. Follow along in the [video](https://www.youtube.com/@mjtechguy) or use the [examples linked here.](examples/terraform/)

---

## About MJ

My name is Mike Johnson. You can call me MJ. I have been working in technology for over 20+ years and have a vast amount of experience in many areas of technology, mostly from the Infrastructure and Operations side.

I have some container certs (Docker and Kubernetes), a few cloud certs (5 AWS and 1 Azure), and spend most of my time these days building robust cloud, container, cybersecurity automation tooling and educational content.

Feel free to connect with me and I look forward to hearing from you.

- **Github:** https://github.com/mjtechguy
- **Youtube:** https://www.youtube.com/@mjtechguy
- **LinkedIn:** https://www.linkedin.com/in/mjtechguy/
- **Website:** https://mjtechguy.com

