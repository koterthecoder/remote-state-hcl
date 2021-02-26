# Remote State Data using Terraform

State is local by default

Using a remote state safeguards the state data and allows for team collaboration

### AWS backend options

<table>
    <tr>
        <td></td>
        <td>Workspaces</td>
        <td>Locking</td>
        <td>GranularControl</td>
        <td>Encryption</td>
    </tr>
    <tr>
        <td>s3</td>
        <td>X</td>
        <td></td>
        <td>X</td>
        <td>X</td>
    </tr>
    <tr>
        <td>DynamoDB</td>
        <td>X</td>
        <td>X</td>
        <td></td>
        <td></td>
    </tr>
</table>


### Authentication Methods

s3: Instance Profile, Access/Secret Keys, Credentials File, Session Token


## Remote State Model

- Infrastructure s3 bucket
- Infrastructure DynamoDB table
- IAM Group (Full access) 
    - Bucket
    - Table
- IAM Group (Read only)
    - Bucket

## Operation Instructions

### Set Profile

**Linux**
```export AWS_PROFILE=infra```

**Windows**
```$env:AWS_PROFILE="infra"```


### initialize the tf configuration
```terraform init```

### validate tf configuration
```terraform validate```

### plan the tf deployment
```terraform plan -out state.tfplan```

### apply the deployment
```terraform apply "state.tfplan"```
