# FHIR Data Processing Lambda Function

This repository contains a Lambda function designed to handle POST requests with JSON payloads based on the FHIR (Fast Healthcare Interoperability Resources) standard. The Lambda function processes these requests, extracts relevant data, and saves the information into a PostgreSQL database.

## Getting Started

To deploy and run this function in your AWS environment, follow these instructions.

### Prerequisites

- AWS CLI already configured with Administrator permission
- Python 3.x installed on your machine
- PostgreSQL database set up with the necessary schema

### Installing

1. **Clone the repository**

   ```bash
   git clone https://github.com/yourusername/fhir-lambda.git
   cd fhir-lambda
   ```

2. Set up a virtual environment

```bash
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
```

3. Install required packages

```bash
pip install -r requirements.txt

```

**4. Set environment variables**

Copy .env.example to .env and update the PostgreSQL database credentials and other necessary details.

**5. Deploy to AWS Lambda**

You can use AWS CLI or any CI/CD pipeline to deploy the function to AWS Lambda.

### Configuration

Make sure your Lambda function has access to the PostgreSQL database and is triggered correctly via API Gateway or another integration.

### Usage

Send a POST request with a JSON FHIR payload to the endpoint provided by AWS API Gateway linked to your Lambda function.

### Example Request

```json
{
  "body": "{\"resourceType\":\"Bundle\",\"type\":\"transaction\",\"entry\":[{\"resource\":{\"resourceType\":\"Patient\",\"name\":[{\"family\":\"Doe\",\"given\":[\"John\"]}],\"gender\":\"male\"}}]}"
}
```

### Development

Modify the Lambda function or its dependencies as required. For local testing, use the provided sample data in data/event1.json.

### Contributing

Contributions are welcome! Please read the contributing guide on how to propose bugfixes, improvements, or open issues.
