# LOGDOWN - Log Aggregator Service

LOGDOWN is a log aggregator service designed to collect, ingest, and filter logs from various sources. It provides a scalable solution for handling large volumes of logs and allows users to query and retrieve logs based on specified filters. The service is built with a focus on flexibility, scalability, and ease of integration with different log sources.

## Features

- Ingest logs from different services like AWS CloudWatch, Kafka, third-party services, etc.
- Support for parsing logs in various formats to normalize the data.
- API endpoint for filtering and querying logs based on customerId and log level.
- Horizontal scalability to handle a growing number of log sources efficiently.
- Optional integration with OpenTelemetry for standardized log collection and exporting.

## Getting Started

These instructions will help you set up and run the LOGDOWN log aggregator service on your local machine.

### Prerequisites

- Python (version 3.6 or higher)
- Docker (optional, required only if using containerization)

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/bjrgo8/logdown.git
   cd logdown
Create and activate a virtual environment (optional but recommended):

bash
Copy code
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
Install the required dependencies:

bash
Copy code
pip install -r requirements.txt
Configuration
Before running the service, you may need to configure certain settings. Modify the configuration files (e.g., config.py) according to your requirements.

Usage
Start the log aggregator service:

bash
Copy code
python app.py
Alternatively, if you prefer to use Docker:

bash
Copy code
docker build -t logdown .
docker run -p 5000:5000 logdown
The log aggregator service should now be running at http://localhost:5000.

Ingest logs from your desired sources by configuring log collectors to forward logs to the service's ingestion endpoint.

Use the provided API endpoints to query and retrieve logs based on filters.

API Endpoints
/ingest: Endpoint for ingesting logs from various sources.
/logs: Endpoint for querying logs based on filters (customerId and log level).
OpenTelemetry Integration (Bonus)
If you wish to enable OpenTelemetry integration, follow these additional steps:

Install the required OpenTelemetry dependencies:

bash
Copy code
pip install opentelemetry-api opentelemetry-sdk opentelemetry-exporter-otlp opentelemetry-instrumentation
Configure OpenTelemetry in the log aggregator service. Refer to the OpenTelemetry documentation for guidance on how to enable logging and tracing.

Scaling
For scaling the log aggregator service horizontally, you can deploy multiple instances of the service and use a load balancer to distribute incoming log traffic.

Contributing
Contributions are welcome! Please fork the repository and create a pull request for any improvements or fixes you'd like to make.

License
This project is licensed under the MIT License.

Acknowledgments
OpenTelemetry - Optional integration for log collection and exporting.
Elasticsearch - Used for storing and indexing logs.
