# DBT + AWS Glue
Usage for proof of concept

### Using the starter project
Is necessary do you have installed and configured:
 - AWS Account
 - AWS CLI
 - Python 3.7.2 or bigger

In this project was utilized *Poetry* for virtual enviroment

### Steps

In target directory execute: commands
```bash
$ poetry --version
$ poetry init
```
Insert the informations about the project and packages python necessaries


After, start the virtual enviroment and install dependecies: commands
```bash
$ poetry shell
$ poetry install
```

Prerequisit: export variables
```bash
$ export DBT_ROLE_ARN="arn:aws:iam::$(aws sts get-caller-identity --query "Account" --output text):role/GlueInteractiveSessionRole"
$ export DBT_S3_LOCATION="s3://aws-dbt-glue-datalake-$(aws sts get-caller-identity --query "Account" --output text)-us-east-1/"
```

Ensure your profile is setup correctly from the command line:
```bash
$ dbt debug --profiles-dir profile
```

Run the models:
```bash
$ dbt run --profiles-dir profile
```

Generate documentation for the project:
```bash
$ dbt docs generate --profiles-dir profile
```

View the documentation for the project:
```bash
$ dbt docs serve --profiles-dir profile
```
### Python Dependecies:
 - aws-glue-sessions
 - boto3
 - dbt-core
 - dbt-glue


### Resources:
- Learn more about dbt [in the docs](https://docs.getdbt.com/docs/introduction)
- Check out [Discourse](https://discourse.getdbt.com/) for commonly asked questions and answers
- Join the [chat](https://community.getdbt.com/) on Slack for live discussions and support
- Find [dbt events](https://events.getdbt.com) near you
- Check out [the blog](https://blog.getdbt.com/) for the latest news on dbt's development and best practices
- Check out [AWS Link](https://aws.amazon.com/pt/blogs/big-data/build-your-data-pipeline-in-your-aws-modern-data-platform-using-aws-lake-formation-aws-glue-and-dbt-core/) for create a modern stack with dbt

- Check out [AWS CLI](https://aws.amazon.com/pt/cli/) for a configure AWS CLI
