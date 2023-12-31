## DSF-CLI - Secret Managers:
Example payloads for Secret Managers
[Click here](https://github.com/imperva/dsf-cli/tree/main/dsfcli/docs/secrets_managers/examples) for example payloads for optional and required fields for all secret manager types.

### Usage:
`dsf secret_manager -h`

### List all secret_managers:
`dsf secret_manager read`

### Retrieve a specific secret_manager by id:
`dsf secret_manager read "<asset_id>"`<br /><br />
`dsf secret_manager read "my.hashicorp.vault.server.com"`

### Create a secret_manager from input string:
`dsf secret_manager create '<json-object>'`<br /><br />
`dsf secret_manager create '{"data": {"assetData": {"asset_display_name": "some-hashicorp-vault-server","asset_id": "my.hashicorp.vault.server.com","Server Host Name": "my.hashicorp.vault.server.com","Server IP": "1.2.3.4","Server Port": "8200","admin_email": "ba@imperva.com","connections": [{"reason": "default","connectionData": {"auth_mechanism": "ec2","role_name": "vault-role-for-ec2"}}]},"serverType": "HASHICORP","parentAssetId": "","gatewayId": "e33bfbe4-a93a-c4e5-8e9c-6e5558c2e2cd"}}'`

### Create a secret_manager from local file:
`dsf secret_manager create '<json-object>'`<br /><br />`dsf secret_manager create "$(cat < secret_manager_AWS.json)"`

### Update a data_source from input string by id:
`dsf secret_manager update "<asset_id>" '<json-object>'`<br /><br />
`dsf secret_manager update "my.hashicorp.vault.server.com" '{"data": {"assetData": {"asset_display_name": "some-hashicorp-vault-server","asset_id": "my.hashicorp.vault.server.com","Server Host Name": "my.hashicorp.vault.server.com","Server IP": "1.2.3.4","Server Port": "8200","admin_email": "ba@imperva.com","connections": [{"reason": "default","connectionData": {"auth_mechanism": "ec2","role_name": "vault-role-for-ec2"}}]},"serverType": "HASHICORP","parentAssetId": "","gatewayId": "e33bfbe4-a93a-c4e5-8e9c-6e5558c2e2cd"}}'`

### Update a secret_manager from local file by id:
`dsf secret_manager update "<asset_id>" '<json-object>'`<br /><br />
`dsf secret_manager update "$(cat < secret_manager_AWS.json)" "my.hashicorp.vault.server.com"`

### Delete a secret_manager by id:
`dsf secret_manager delete "<asset_id>" '<json-object>'`<br /><br />
`dsf secret_manager delete "my.hashicorp.vault.server.com"`

#### Config Options ####

`data.admin_email` [string] - _(required)_ The email address to notify about this asset Default Value: null

`data.arn` [string] - _(required)_ Amazon Resource Name - format is arn:partition:service:region:account-id and used as the asset_id Default Value: ""

`data.asset_display_name` [string] - _(required)_ User-friendly name of the asset, defined by user. Default Value: ""

`data.asset_id` [string] - _(required)_  Default Value: null

`data.asset_source` [string] - _(optional)_ The source platform/vendor/system of the asset data. Usually the service responsible for creating that asset document Default Value: ""

`data.available_regions` [string] - _(optional)_ A list of regions to use in discovery actions that iterate through region Default Value: null

`data.aws_proxy_config` [map] - _(optional)_ AWS specific proxy configuration Default Value: null

`data.credentials_endpoint` [string] - _(optional)_ A specific sts endpoint to use Default Value: null

`data.criticality` [options] - _(optional)_ The asset's importance to the business. These values are measured on a scale from "Most critical" (1) to "Least critical" (4). Allowed values: 1, 2, 3, 4 Default Value: null

`data.gateway_id` [string] - _(required)_  Default Value: null

`data.jsonar_uid` [string] - _(optional)_ Unique identifier (UID) attached to the Sonar machine controlling the asset Default Value: null

`data.location` [string] - _(optional)_ Current human-readable description of the physical location of the asset, or region. Default Value: null

`data.managed_by` [string] - _(optional)_ Email of the person who maintains the asset; can be different from the owner specified in the owned_by field. Defaults to admin_email. Default Value: null

`data.owned_by` [string] - _(optional)_ Email of Owner / person responsible for the asset; can be different from the person in the managed_by field. Defaults to admin_email. Default Value: null

`data.proxy` [string] - _(optional)_ Proxy to use for AWS calls if aws_proxy_config is populated the proxy field will get populated from the http value there Default Value: null

`data.region` [string] - _(optional)_ For cloud systems with regions, the default region or region used with this asset Default Value: null

`data.server_host_name` [string] - _(required)_ Hostname (or IP if name is unknown) Default Value: null

`data.server_port` [string] - _(optional)_  Default Value: "16114"

`data.service_endpoints` [map] - _(optional)_ Specify particular endpoints for a given service in the form of <service name>: "endpoint" Default Value: null

`data.used_for` [options] - _(optional)_ Designates how this asset is used / the environment that the asset is supporting. Default Value: null Possible Values: Production`, `Test`, `Development`, `Demonstration`, `QA`, `Staging`, `Training`, `Disaster Recovery

`data.version` [string] - _(optional)_ Denotes the version of the asset Default Value: null

`data.connections[].connectionData.access_id` [string] - _(required)_ The Access key ID of AWS secret access key used to authenticate Default Value: null

`data.connections[].connectionData.amazon_secret` [map] - _(optional)_ Configuration to integrate with AWS Secrets Manager Default Value: null

`data.connections[].connectionData.ca_certs_path` [string] - _(optional)_ Certificate authority certificates path; what location should the sysetm look for certificate information from. Equivalent to --capath in a curl call Default Value: null

`data.connections[].connectionData.cert_file` [string] - _(optional)_  Default Value: null

`data.connections[].connectionData.credential_fields` [map] - _(optional)_ Document containing values to build a profile from. Filling this will create a profile using the given profile name Default Value: null

`data.connections[].connectionData.external_id` [string] - _(optional)_ External ID to use when assuming a role Default Value: null

`data.connections[].connectionData.hashicorp_secret` [map] - _(optional)_ Configuration to integrate with HashiCorp Vault Default Value: null

`data.connections[].connectionData.key_file` [string] - _(optional)_  Default Value: null

`data.connections[].connectionData.region` [string] - _(required)_ Default AWS region for this asset Default Value: null

`data.connections[].connectionData.role_name` [string] - _(required)_ Role to use for authentication Default Value: null

`data.connections[].connectionData.secret_key` [string] - _(required)_ The Secret access key used to authenticate Default Value: null

`data.connections[].connectionData.self_signed` [bool] - _(optional)_  Default Value: null

`data.connections[].connectionData.ssl` [bool] - _(optional)_ If true, use SSL when connecting Default Value: null

`data.connections[].connectionData.username` [string] - _(required)_ The name of a profile in /imperva/local/credentials/.aws/credentials to use for authenticating Default Value: null
