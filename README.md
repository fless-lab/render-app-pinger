# Render App Pinger

This project uses GitHub Actions to automatically ping multiple applications hosted on Render.com, preventing them from sleeping due to inactivity on free plans.

## Features

- Automatically pings Render apps every 10 minutes
- Supports multiple app URLs
- Uses GitHub Secrets for secure storage of app URLs
- Provides logs to check the status of each ping

## Setup

1. Fork or clone this repository.
2. Go to your repository's Settings > Secrets and variables > Actions.
3. Create a new repository secret named `APP_URLS`.
4. Set the value of `APP_URLS` to a JSON array of your Render app URLs, e.g.:
   ```json
   ["https://app1.onrender.com", "https://app2.onrender.com", "https://app3.onrender.com"]
   ```
5. The GitHub Action will automatically run on the schedule defined in the workflow file.

## Workflow File

The `.github/workflows/main.yml` file contains the GitHub Actions workflow definition. It's set to run every 10 minutes and can also be triggered manually.

## Monitoring

- Go to the "Actions" tab in your GitHub repository to view the workflow runs.
- Each run will show the status of pings to your Render apps.

## Customization

- You can modify the schedule in the `.github/workflows/main.yml` file.
- To add or remove apps, update the `APP_URLS` secret in your repository settings.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is open source and available under the [MIT License](LICENSE).
