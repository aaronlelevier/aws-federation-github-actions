# STEPS

Summarizing steps so this is repeatable

## Start

Following this blog: https://awsteele.com/blog/2021/09/15/aws-federation-comes-to-github-actions.html

Using [saws](https://github.com/donnemartin/saws) to run commands via AWS CLI.

Created virtualenv, and install saws:

```bash
python3 -m venv ~/.virtualenv/aws

source ~/.virtualenv/aws/bin/activate

pip install saws
```

Create Role

```bash
aws cloudformation deploy --template-file role.yml --stack-name ExampleGithubRole --capabilities CAPABILITY_NAMED_IAM
```

Provision secret at the repo level, not environment, for the Github repo.

Deploy example.yml action.

It works!

`aws` CLI comes installed, no need to run install commands in the Github Action.
