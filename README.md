# icloudservice

 [![Publish icloudservice](https://github.com/leonardogonzalolaura/workspace_icloudservice/actions/workflows/publish.yml/badge.svg)](https://github.com/leonardogonzalolaura/workspace_icloudservice/actions/workflows/publish.yml)
 
 ![PyPI version](https://img.shields.io/pypi/v/icloudservice.svg)


**`icloudservice`** is a Python library for cloud integration services with AWS and Azure. This library helps streamline cloud service interactions and management.

## Features

- Integration with AWS and Azure cloud services.
- Provides easy-to-use methods for interacting with cloud resources.

## Installation

You can install `icloudservice` via pip:

```bash
pip install icloudservice
```

## API Reference

### `icloudservice` Module

#### `Provider` Class

The `Provider` class is used to create cloud service clients for AWS and Azure. It provides methods to initialize clients with appropriate credentials and configurations.

**Methods:**

- **`AWS(access_key: str, secret_key: str,region: str = None) -> AWSCloud`**

  Initializes an AWS Cloud client with the provided access key and secret key.

  **Parameters:**
  - `access_key` (str): AWS access key ID.
  - `secret_key` (str): AWS secret access key.
  - `region` (str,optional): The AWS region to use. Default to None.

  **Returns:**
  - An instance of the `AWSCloud` class.

- **`AZURE(subscription_id) -> AzureCloud`**

  Initializes an Azure Cloud client with the provided subscription ID.

  **Parameters:**
  - `subscription_id`: Azure subscription ID.

  **Returns:**
  - An instance of the `AzureCloud` class.

#### `AWSCloud` Class

Provides access to various AWS cloud services.

**Methods:**

- **`S3Service(bucket_name: str,region: str = None)`**

  Provides access to AWS S3 service.

  **Parameters:**
  - `bucket_name` (str): The name of the S3 bucket.
  - `region` (str): The region of the S3 bucket to use.Default to None.

  **Returns:**
  - An instance of the `S3Service` class.

- **`EC2Service()`**

  Provides access to AWS EC2 service.

  **Returns:**
  - An instance of the `EC2Service` class.

- **`LambdaService()`**

  Provides access to AWS Lambda service.

  **Returns:**
  - An instance of the `LambdaService` class.

- **`SNSService()`**

  Provides access to AWS SNS service.

  **Returns:**
  - An instance of the `SNSService` class.

- **`SQSService()`**

  Provides access to AWS SQS service.

  **Returns:**
  - An instance of the `SQSService` class.

#### `AzureCloud` Class

Provides access to various Azure cloud services.

**Methods:**

- **`BlobService()`**

  Provides access to Azur


**Example:**

```python
from icloudservice import Provider

# Initialize Provider
provider = Provider()

# Create AWS service client
aws_services = provider.AWS(access_key='your-access-key-id', secret_key='your-secret-access-key')

# Access S3 service
s3_service = aws_services.S3Service('bucket_name')

# Access EC2 service
ec2_service = aws_services.EC2Service()

# Access Lambda service
lambda_service = aws_services.LambdaService()

# Access SNS service
sns_service = aws_services.SNSService()

# Access SQS service
sqs_service = aws_services.SQSService()

```
```python
from icloudservice import Provider

# Initialize Provider
provider = Provider()

# Create Azure service client
azure_services = provider.AZURE(subscription_id='your-subscription-id')

# Access Azure Blob Storage service
blob_service = azure_services.BlobService()

# Access Azure Virtual Machines service
vm_service = azure_services.VMService()

# Access Azure Functions service
functions_service = azure_services.FunctionsService()

# Access Azure Event Hubs service
event_hubs_service = azure_services.EventHubsService()

# Access Azure Service Bus service
service_bus_service = azure_services.ServiceBusService()
```


## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
