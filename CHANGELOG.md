# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.5.0] - 2019-04-15
### Breaking
- Clusters will now default to using KIAM for IAM roles. This requires KIAM to be active in your cluster for pods to use IAM role permissions. If you are deploying demo clusters this can be disabled via `enable_kiam`

### Added
- Added support for EKS Control Plane logs to Cloudwatch. Defaults to all logs enabled. 

### Fixed
- Resolved issue where Launch Template based ASG's could not be scaled from 0. 

## [0.4.0] - 2019-03-26
### Breaking
- Removed instance_type_3 support. This was hard to use in practice as cluster-autoscaler expects all instances in an ASG to have the same CPU/Memory characteristics. instance_type_2 has been left as for most instance types Amazon has the previous instance generation available which has the same CPU/Memory characteristics. For example M4/M5 Large instances both have 2 vCPU and 8GB of memory available so can share an ASG without impacting cluster-autoscaler. 

### Fixed 
- Add cluster owned tag on the default worker security group so the ELB controller is able to find it when multiple security groups are applied to nodes

### Added
- Add support for EKS Public/Private endpoint configuration
- Add support for specifying subnets per ASG to work around PV scheduling limitations

## [0.3.0] - 2019-03-15
### Added
- suspended_processes on worker groups
- enabled_metrics on worker groups

## [0.2.0] - 2019-03-01
- Added Velero Support
- Resolved issue with using aws_subnet_ids datasource for private_subnets

## [0.1.0] - 2019-02-09
### Added
- Everything
