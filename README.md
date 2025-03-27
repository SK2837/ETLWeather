# Astronomer Airflow Project

<img src="https://raw.githubusercontent.com/astronomer/docs/main/static/img/astronomer-logo.svg" alt="Astronomer Logo" width="300"/>

## 🚀 Introduction

Welcome to your Astronomer Airflow project! This repository was generated automatically when you ran `astro dev init` using the Astronomer CLI. It contains everything you need to develop and run Apache Airflow workflows locally and deploy them to Astronomer.

## 📁 Project Structure

```
.
├── dags/                  # Your Airflow DAGs live here
│   └── example_astronauts.py  # Example DAG that queries astronauts in space
├── include/               # Additional files to include in your project
├── plugins/               # Custom or community Airflow plugins
├── Dockerfile             # Customizes the Astro Runtime Docker image
├── packages.txt           # OS-level dependencies (apt packages)
├── requirements.txt       # Python dependencies (pip packages)
└── airflow_settings.yaml  # Local Airflow configurations
```

### DAGs

The `dags/` directory contains your Airflow DAG files. The example DAG demonstrates:

- ETL pipeline using the TaskFlow API
- Dynamic task mapping to process multiple items
- API integration with the Open Notify API
- Best practices for structuring Airflow code

## 🔧 Getting Started

### Prerequisites

- [Docker](https://docs.docker.com/get-docker/)
- [Astronomer CLI](https://docs.astronomer.io/astro/cli/install-cli)

### Local Development

1. **Start Airflow locally**:

   ```bash
   astro dev start
   ```

   This command spins up four Docker containers:
   - **Postgres**: Metadata database (port 5432)
   - **Webserver**: Airflow UI (port 8080)
   - **Scheduler**: Monitors and triggers tasks
   - **Triggerer**: Handles deferred task execution

2. **Verify installation**:

   ```bash
   docker ps
   ```

   You should see all four containers running.

3. **Access Airflow UI**:
   - URL: [http://localhost:8080](http://localhost:8080)
   - Username: `admin`
   - Password: `admin`

4. **Start developing**:
   - Add new DAGs to the `dags/` folder
   - Install dependencies in `requirements.txt`
   - Add plugins to the `plugins/` folder

5. **Stopping Airflow**:

   ```bash
   astro dev stop
   ```

## 🛠️ Common Commands

```bash
# View logs for your local Airflow environment
astro dev logs

# Access the Airflow CLI
astro dev bash

# Restart your local Airflow environment
astro dev restart

# Run tests on your DAGs
astro dev pytest

# View logs for a specific container
astro dev logs --scheduler
```

## 📦 Adding Dependencies

- **Python packages**: Add them to `requirements.txt`
- **OS-level packages**: Add them to `packages.txt`
- **Custom environment variables**: Add them to your Dockerfile
- **Connections/Variables**: Add them to `airflow_settings.yaml`

## 🌐 Deployment

### Deploying to Astronomer Cloud

1. **Authenticate with Astronomer**:

   ```bash
   astro login
   ```

2. **List your Astronomer workspaces**:

   ```bash
   astro workspace list
   ```

3. **Deploy your project**:

   ```bash
   astro deploy
   ```

For detailed deployment instructions, visit the [Astronomer documentation](https://www.astronomer.io/docs/astro/deploy-code/).

## 📚 Learning Resources

- [Airflow Documentation](https://airflow.apache.org/docs/)
- [Astronomer Documentation](https://docs.astronomer.io/)
- [Airflow Guides](https://www.astronomer.io/guides/)
- [Airflow Webinars](https://www.astronomer.io/events/)
- [Astronomer Registry](https://registry.astronomer.io/) (pre-built DAGs, operators, and more)

## 🆘 Need Help?

- [Astronomer Community Forum](https://forum.astronomer.io/)
- [Astronomer Support](https://support.astronomer.io/)
- [Airflow Slack](https://apache-airflow.slack.com/)

## 📝 Contributing

We welcome contributions to improve this project template! Please open an issue or submit a pull request to the [Astronomer CLI repository](https://github.com/astronomer/astro-cli).

---

Built with ❤️ by [Astronomer](https://www.astronomer.io/)
