Fluentd Benchmark Azure Environment with Terraform
===

[![Build Status](https://travis-ci.com/fluent-plugins-nursery/fluentd-benchmark-azure-environment.svg?branch=master)](https://travis-ci.com/fluent-plugins-nursery/fluentd-benchmark-azure-environment)

## Prerequisites

* Terraform 0.12+
* Python3 3.6+
* Ansible 2.9+
* make

## Setup

 1. Prepare RSA public key and put it into `azure_key/id_rsa_azure.pub`.
 2. Prepare env.sh and fill `ARM_` prefixed environment variables with your credentials.
 3. Run `env.sh`
 4. Change directory to target environments(winevtlog_bench/in_tail_bench).
 5. Specify user-defined variables in `terraform.tfvars` which can be copied from `terraform.tfvars.sample` and fill them for each environment (winevtlog\_bench, in\_tail\_bench).


### Note about env.sh configuration

* `ARM_SUBSCRIPTION_ID` - You can get by `az account list` if you already logged in.
* `ARM_TENANT_ID` - You can get by `az account list` if you already logged in.
* `ARM_CLIENT_ID` - You can get by creating service principal.
* `ARM_CLIENT_SECRET` - You can get by creating service principal.

You can create service principal by `az ad sp create-for-rbac --name FOOBAR` or something. You need to logged in as user account in beforehand.

## Usage

### Prepare Python libraries

```
$ pip install -r requirements.txt
```

Or, creating virtual environment wirth venv

```
$ python3 -m venv management
```

And then,

```
$ source management/bin/activate
$ pip install -r requirements.txt
```

### Windows EventLog Scenario Benchmark

See [README.md](winevtlog_bench/README.md) about details.

### in\_tail Scenario Benchmark

See [README.md](in_tail_bench/README.md) about details.


### in\_syslog Scenario Benchmark

See [README.md](in_syslog_bench/README.md) about details.


### in\_sample_systemlog Scenario Benchmark

See [README.md](in_sample_systemlog/README.md) about details.


## License

[MIT](LICENSE).
