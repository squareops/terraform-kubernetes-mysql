## Mysql Example
![squareops_avatar]

[squareops_avatar]: https://squareops.com/wp-content/uploads/2022/12/squareops-logo.png

### [SquareOps Technologies](https://squareops.com/) Your DevOps Partner for Accelerating cloud journey.
<br>
This example will be very useful for users who are new to a module and want to quickly learn how to use it. By reviewing the examples, users can gain a better understanding of how the module works, what features it supports, and how to customize it to their specific needs.
<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Requirements

No requirements.

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider\_aws) | n/a |
| <a name="provider_helm"></a> [helm](#provider\_helm) | n/a |
| <a name="provider_kubernetes"></a> [kubernetes](#provider\_kubernetes) | n/a |
| <a name="provider_random"></a> [random](#provider\_random) | n/a |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [aws_iam_role.mysql_backup_role](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_role) | resource |
| [aws_secretsmanager_secret.mysql_user_password](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/secretsmanager_secret) | resource |
| [aws_secretsmanager_secret_version.mysql_user_password](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/secretsmanager_secret_version) | resource |
| [helm_release.mysqldb](https://registry.terraform.io/providers/hashicorp/helm/latest/docs/resources/release) | resource |
| [helm_release.mysqldb_backup](https://registry.terraform.io/providers/hashicorp/helm/latest/docs/resources/release) | resource |
| [kubernetes_namespace.mysqldb](https://registry.terraform.io/providers/hashicorp/kubernetes/latest/docs/resources/namespace) | resource |
| [random_password.mysqldb_custom_user_password](https://registry.terraform.io/providers/hashicorp/random/latest/docs/resources/password) | resource |
| [random_password.mysqldb_exporter_user_password](https://registry.terraform.io/providers/hashicorp/random/latest/docs/resources/password) | resource |
| [random_password.mysqldb_replication_user_password](https://registry.terraform.io/providers/hashicorp/random/latest/docs/resources/password) | resource |
| [random_password.mysqldb_root_password](https://registry.terraform.io/providers/hashicorp/random/latest/docs/resources/password) | resource |
| [aws_caller_identity.current](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/caller_identity) | data source |
| [aws_eks_cluster.kubernetes_cluster](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/eks_cluster) | data source |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_app_version"></a> [app\_version](#input\_app\_version) | App version | `string` | `"8.0.29-debian-11-r9"` | no |
| <a name="input_chart_version"></a> [chart\_version](#input\_chart\_version) | Chart version | `string` | `"9.2.0"` | no |
| <a name="input_cluster_name"></a> [cluster\_name](#input\_cluster\_name) | Name of the EKS cluster | `string` | `""` | no |
| <a name="input_mysqldb_backup_config"></a> [mysqldb\_backup\_config](#input\_mysqldb\_backup\_config) | Mysql Backup configurations | `any` | <pre>{<br>  "aws_access_key_id": "AKIAT6J7AJ7XMR7TDC7R",<br>  "aws_secret_access_key": "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",<br>  "cron_for_full_backup": "*/5 * * * *",<br>  "s3_bucket_region": "us-east-2",<br>  "s3_bucket_uri": "s3://mysqlbackupp"<br>}</pre> | no |
| <a name="input_mysqldb_backup_enabled"></a> [mysqldb\_backup\_enabled](#input\_mysqldb\_backup\_enabled) | Set true to enable mysql backups | `bool` | `false` | no |
| <a name="input_mysqldb_config"></a> [mysqldb\_config](#input\_mysqldb\_config) | Mysql configurations | `any` | <pre>{<br>  "architecture": "",<br>  "custom_user_username": "",<br>  "environment": "",<br>  "name": "",<br>  "primary_pod_volume_size": "",<br>  "secondary_pod_replica_count": 1,<br>  "secondary_pod_volume_size": "",<br>  "storage_class_name": "",<br>  "values_yaml": ""<br>}</pre> | no |
| <a name="input_mysqldb_exporter_enabled"></a> [mysqldb\_exporter\_enabled](#input\_mysqldb\_exporter\_enabled) | Set true to deploy mysqldb exporters to get metrics in grafana | `bool` | `false` | no |
| <a name="input_namespace"></a> [namespace](#input\_namespace) | Namespace name | `string` | `"mysqldb"` | no |
| <a name="input_recovery_window_aws_secret"></a> [recovery\_window\_aws\_secret](#input\_recovery\_window\_aws\_secret) | Number of days that AWS Secrets Manager waits before it can delete the secret. This value can be 0 to force deletion without recovery or range from 7 to 30 days. | `number` | `0` | no |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_mysql_port"></a> [mysql\_port](#output\_mysql\_port) | n/a |
| <a name="output_mysql_primary_endpoint"></a> [mysql\_primary\_endpoint](#output\_mysql\_primary\_endpoint) | n/a |
| <a name="output_mysql_primary_headless_endpoint"></a> [mysql\_primary\_headless\_endpoint](#output\_mysql\_primary\_headless\_endpoint) | n/a |
| <a name="output_mysql_secondary_endpoint"></a> [mysql\_secondary\_endpoint](#output\_mysql\_secondary\_endpoint) | n/a |
| <a name="output_mysql_secondary_headless_endpoint"></a> [mysql\_secondary\_headless\_endpoint](#output\_mysql\_secondary\_headless\_endpoint) | n/a |
<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->

