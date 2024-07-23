---
layout: default
title: Prolific Survey
nav_order: 7
---

# Prolific Survey

We have developed two distinct formats for conducting Prolific surveys. You can find them at the following repositories:

- [Main Survey Format](https://github.com/Etelis/Prolific-HRI-Survey/tree/main)
- [First Survey Finding Features](https://github.com/Etelis/Prolific-HRI-Survey/tree/bystander/first_survey_finding_features)

## Running the Surveys

Both survey formats are React projects. To run them, you need to build the projects first and then deploy them on a cloud platform. We recommend using AWS Amplify for this purpose.

### Building the Project

1. Clone the repository:
   ```bash
   git clone <repository_url>
   cd <repository_directory>
   ```

2. Install the dependencies:
   ```bash
   npm install
   ```

3. Build the project:
   ```bash
   npm run build
   ```

### Deploying on AWS Amplify

1. **Sign in to AWS Amplify Console:**
   Go to the [AWS Amplify Console](https://console.aws.amazon.com/amplify/home).

2. **Create a New App:**
   - Click on "Get Started" under "Deploy".
   - Connect your GitHub repository and select the branch you want to deploy.

3. **Configure the Build Settings:**
   - AWS Amplify will detect the build settings from your project automatically. Review and adjust if necessary.

4. **Deploy the App:**
   - Click "Save and Deploy". AWS Amplify will build and deploy your application.

### REST Backend Integration

Inside the projects, there is an expected URL for the REST backend. Here is an example of how the frontend communicates with the backend:

```javascript
fetch("https://24d6houomeioliarmgrwonbi7m0nmblf.lambda-url.eu-central-1.on.aws/", {
    method: "POST",
    headers: { "Content-Type": "application/json" },
    body: JSON.stringify(completedSurveyData)
})
.then(response => response.json())
.then(data => {
    if (data.completionLink) {
        window.location.href = data.completionLink;
    }
})
.catch(error => console.error('Error:', error));
```

### REST Backend Functionality

The REST backend should support the following functionalities based on the provided code:

```python
import json
import boto3
import os
from botocore.exceptions import ClientError

def lambda_handler(event, context):
    # Environment variables
    table_name = os.environ.get('DYNAMODB_TABLE_NAME')
    completion_link = os.environ.get('PROLIFIC_COMPLETION_LINK')

    # Check if environment variables are set
    if not table_name or not completion_link:
        return {
            'statusCode': 500,
            'body': json.dumps('Error: Environment variables not set correctly.')
        }

    # Parse the incoming data
    try:
        print(event)
        request_data = json.loads(event['body'])
        survey_data = request_data
    except (KeyError, json.JSONDecodeError):
        return {
            'statusCode': 400,
            'body': json.dumps('Error: Invalid input data format.')
        }

    # Initialize a DynamoDB client
    dynamodb = boto3.resource('dynamodb')
    table = dynamodb.Table(table_name)

    # Check if the Prolific data already exists in the database
    try:
        if survey_data.get('PROLIFIC_PID') and survey_data.get('STUDY_ID') and survey_data.get('SESSION_ID'):
            response = table.get_item(
                Key={
                    'PROLIFIC_PID': survey_data['PROLIFIC_PID'],
                    'SESSION_ID': survey_data['SESSION_ID']
                }
            )
            if 'Item' in response:
                # Data already exists, return an error message
                return {
                    'statusCode': 400,
                    'body': json.dumps('Error: Survey data for this user already exists.')
                }
        else:
            return {
                'statusCode': 400,
                'body': json.dumps('Error: Missing Prolific ID, Study ID, or Session ID.')
            }
    except ClientError as e:
        # Handle potential errors in querying the database
        return {
            'statusCode': 500,
            'body': json.dumps(f"Error accessing database: {e.response['Error']['Message']}")
        }

    # Save the new data to DynamoDB
    try:
        table.put_item(Item=survey_data)
    except ClientError as e:
        # Handle potential errors in inserting data
        return {
            'statusCode': 500,
            'body': json.dumps(f"Error saving data to database: {e.response['Error']['Message']}")
        }

    # Return success message along with the Prolific completion link
    return {
        'statusCode': 200,
        'body': json.dumps({'message': 'Survey data saved successfully.', 'completionLink': completion_link})
    }
```

Ensure that the REST backend is set up correctly to handle survey data and return the Prolific completion link.
