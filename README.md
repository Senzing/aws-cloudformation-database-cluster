# aws-cloudformation-database-cluster

## Synopsis

The
`aws-cloudformation-database-cluster`
AWS Cloudformation template creates an AWS VPC
and Aurora Postgres serverless database deployment.
The Cloudformation does not deploy Senzing.
Rather, it deploys a database than can be used by other AWS Cloudformations
which do deploy Senzing such as
[aws-cloudformation-ecs-senzing-stack-basic](https://github.com/Senzing/aws-cloudformation-ecs-senzing-stack-basic).

## How to deploy without much thinking

For more details, see [details of deployment](docs/README.md).

1. :warning: **Warning:** This Cloudformation deployment will accrue AWS costs.
   With appropriate permissions, the
   [AWS Cost Explorer](https://aws.amazon.com/aws-cost-management/aws-cost-explorer/)
   can help evaluate costs.
1. Download the appropriate [AWS Cloudformation template example](https://raw.githubusercontent.com/Senzing/aws-cloudformation-database-cluster/main/cloudformation.yaml) from this repository to your local device.  Example:
    ```
    curl -X GET \
        --output ~/cloudformation.yaml \
        https://raw.githubusercontent.com/Senzing/aws-cloudformation-database-cluster/main/cloudformation.yaml
    ```
3. It is highly suggested to take a look at the AWS Cloudformation Template that has been downloaded.  This template is an example that deploys and configures a number of services and facilities.  While it is a working and complete example, each business may have different requirements and their account may not have all the privledges required to deploy it.  Furthermore, the examples change over time and these files are meant to be treated as code files so they should be put under source control.
1. Visit the [AWS Cloudformation home](https://console.aws.amazon.com/cloudformation/home).
1. At the upper-right, click the "Create stack" drop-down and choose "With new resources (standard)".
1. In the "Specify template" area choose the "Upload a template file" radio button.
1. Select the "Choose file" button and choose the AWS Cloudformation template that was downloaded previously.1. At lower-right, click on "Next" button.
1. In **Specify stack details**
    1. In **Parameters**
        1. In **Senzing installation**
            1. If speed is desired over lower cost, choose "Multiple".
            1. If lower cost is desired over speed, choose "Single".
        1. In **Security responsibility**
            1. Understand the nature of the security in the deployment.
            1. Once understood, enter "I AGREE".
    1. At lower-right, click "Next" button.
1. In **Configure stack options**
    1. At lower-right, click "Next" button.
1. In **Review senzing-db**
    1. Near the bottom, in **Capabilities**
        1. Check ":ballot_box_with_check: I acknowledge that AWS CloudFormation might create IAM resources."
    1. At lower-right, click "Create stack" button.

## Additional topics

1. [Details of deployment](docs/README.md)
1. [How to migrate an AWS RDS database](https://github.com/Senzing/knowledge-base/blob/main/HOWTO/migrate-aws-rds-database.md)
