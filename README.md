# PostgreSQL Service Deployment

CI/CD setup to deploy PostgreSQL to a VPS using GitHub Actions.

## Structure

- `docker-compose.yml` - PostgreSQL 16.2 Alpine container configuration
- `.github/workflows/deploy.yml` - GitHub Actions workflow for deployment
- `.env.example` - Environment variables template

## Configuration

Set the following GitHub Secrets:
   - `VPS_SSH_KEY` - SSH private key for server access
   - `VPS_HOST` - VPS hostname or IP address
   - `VPS_USER` - SSH username
   - `POSTGRES_USER` - Database user
   - `POSTGRES_PASSWORD` - Database password
   - `POSTGRES_DB` - Database name

## Deployment

Navigate to GitHub Actions and run the workflow manually. Select the target environment.

The workflow will:
1. Connect to your VPS via SSH
2. Create the deployment directory
3. Set up environment variables
4. Copy docker-compose.yml
5. Pull the latest image and restart the service

## Access

PostgreSQL runs on port 5432 of your VPS.
