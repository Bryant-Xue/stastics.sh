# Statsics.sh (Nginx Access Log Analyzer)

A lightweight Bash script designed to analyze Nginx access logs. It offers functionalities to:

- Aggregate traffic and request statistics for each hosted site.
- Identify top IP addresses based on request count and bandwidth usage.
- Extract and save logs related to specific IP addresses.

## 📂 Features

- **Per-Site Statistics**: Summarizes total requests and data transferred for each site.
- **Top IP Analysis**: Lists top 10 IPs by request count and bandwidth consumption for a specified site.
- **IP Log Extraction**: Filters and saves logs associated with a specific IP address across all sites.
- **Human-Readable Output**: Presents data sizes in B, KB, MB, or GB for clarity.

## 🛠️ Usage

Ensure the script has execute permissions:

```bash
chmod +x statics.bash
```

Then, execute the script with the desired option:

### View Statistics for a Specific Site

```bash
./statics.bash -n example.com
```

- Displays the top 10 IPs by request count and bandwidth for `example.com`.

### List All Sites with Summary Statistics

```bash
./statics.bash -v
```

- Provides a summary of all sites, including total requests and data transferred.
- Highlights the top 5 sites based on requests and bandwidth.

### Extract Logs for a Specific IP Address

```bash
./statics.bash -i 1.2.3.4 output.log
```

- Searches all site logs for entries related to IP `1.2.3.4` and saves them to `output.log`.

## 📁 Configuration

By default, the script looks for logs in:

```bash
/opt/1panel/apps/openresty/openresty/www/sites
```

If your Nginx logs are located elsewhere, modify the `LOG_DIR` variable at the beginning of the script:

```bash
LOG_DIR="/path/to/your/nginx/sites"
```

## 📌 Notes

- The script handles both plain text and gzip-compressed (`.gz`) log files.
- Ensure that the log files follow the standard Nginx access log format.
- For large log files, processing might take some time; consider running the script during off-peak hours.

## 📄 License

This project is open-source and available under the MIT License.

## 🤝 Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your enhancements.
