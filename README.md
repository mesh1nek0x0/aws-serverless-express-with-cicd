# Serverless Express with CI/CD sample

[AWS Serverless Express](https://github.com/awslabs/aws-serverless-express) sample with CI/CD(CircleCI)

CircleCI を利用した[Serverless Express](https://github.com/awslabs/aws-serverless-express)の動作サンプルです

## :pushpin: Description

## :white_check_mark: Features

- AWS Serverless Express sample
- deploy from CircleCI

---

## :floppy_disk: Install

### Requirements

- CircleCI 0.1.5607+f705856+
- yarn 1.10.1+
- node 10.10.0+
- aws-cli 1.11.129+
- aws-sam 0.16.1+

### GitHub Repository Setting up

fork this repository

### AWS Setting up

1. add Circle CI IAM User for deploying from CI
1. generate Access Key(Copied)

### CircleCI Setting up

1. Add your CircleCI Project. (build failed, but no problem)
1. Go settings, add AWS Permissions
1. Go settings, add Environment Variable

- AWS_ACCOUNT_ID: your aws account id
- AWS_REGION: region for deploy
- SERVERLESS_EXPLESS_BUCKET: bucket name for upload

Finaly, rebuild CircleCi workflow.

### Access Your Apps

After the setup steps completes, open the AWS CloudFormation console https://console.aws.amazon.com/cloudformation/home and switch to the region you specified. Select the `AwsServerlessExpressStack` stack, then click the `ApiUrl` value under the **Outputs** section - this will open a new page with your running API. The API index lists the resources available in the example Express server (`app.js`), along with example `curl` commands.

## :information_source: Anything else

If you would prefer to delete AWS assets that were just created, run like bellow.

```
$ npm run config -- --account-id="$AWS_ACCOUNT_ID" \
--bucket-name="$SERVERLESS_EXPLESS_BUCKET" \
--region="$AWS_REGION"
$ npm run delete-stack
$ npm run delete-bucket
```

## :pencil: Author

[mesh1nek0x0](https://github.com/mesh1neko)
