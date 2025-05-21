# AWS Infrastructure Security Audit And Reporting Crew
AWS Infrastructure Security Audit And Reporting Crew project, wil help you perform security audits and generate reports for your AWS infrastructure using a multi-agent AI system, leveraging the powerful and flexible framework provided by CrewAI.

## Get Started

### Python Version Requirements

CrewAI requires Python >=3.10 and <3.13. Here's how to check your version(code tested with 3.12):

```bash
python3 --version
```

### Installing CrewAI

1. Install CrewAI with all recommended tools using either method:

```bash
pip install crewai crewai-tools
```

2. For existing installations, upgrade CrewAI:

```bash
pip install --upgrade crewai crewai-tools
```


### Project Setup

1. Clone this repository : `https://github.com/vangve27/aws_sample_agents_poc.git`
2. Set up your environment variables (see Environment Variables section below)
3. Install dependencies with:
    ```bash
    crewai install
    ```

### Customizing
### Environment Variables

A `.env.example` file is provided in the root directory as a template. Copy this file to create your own `.env` file:

```bash
cp .env_old .env
```

Then edit the `.env` file with your actual credentials. The following variables are required:

```env
# AWS Credentials for Bedrock
AWS_REGION_NAME=us-east-1
MODEL=bedrock/anthropic.claude-3-sonnet-20240229-v1:0
SERPER_API_KEY=your_serper_api_key
```

> **Security Note**: Never commit your actual `.env` file to version control. The `.env` file is already included in `.gitignore` to prevent accidental commits of sensitive information.

### AWS Bedrock Setup
1. Ensure you have access to AWS Bedrock in your AWS account
2. Your AWS credentials must have permissions to invoke Bedrock models
3. The specified AWS region must have Bedrock available
4. The model specified in `MODEL` must be enabled in your Bedrock console

### Supported Models
- See [AWS Bedrock documentation](https://docs.aws.amazon.com/bedrock/latest/userguide/model-ids-arns.html) for more models

### Modify the Configuration Files if needed:
- Modify `src/aws_infrastructure_security_audit_and_reporting/config/agents.yaml`
- Modify `src/aws_infrastructure_security_audit_and_reporting/config/tasks.yaml` 
- Modify `src/aws_infrastructure_security_audit_and_reporting/crew.py`
- Modify `src/aws_infrastructure_security_audit_and_reporting/main.py`

## Running the Project

To start your crew of AI agents and begin the AWS security audit, run this from the root folder of your project:

```bash
crewai run
```

This command initializes the AWS Infrastructure Security Audit crew, assembling the agents and assigning them tasks as defined in your configuration.

This example, unmodified, will run the create a `security_report.md` file with the output of a research on LLMs in the root folder.

## Understanding Your Crew

The AWS Infrastructure Security Audit crew is composed of multiple AI agents, each with unique roles, goals, and tools. These agents collaborate on a series of tasks, defined in `config/tasks.yaml`, leveraging their collective skills to perform security audits and generate comprehensive reports. The `config/agents.yaml` file outlines the capabilities and configurations of each agent in your crew.

```Reference
Referenced from AWS_SAMPLES
```
