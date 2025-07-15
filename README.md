# mfloods: HTTP Request Flooder (Binaries & Documentation)

**This repository contains only the compiled binaries and documentation for the `mfloods` HTTP request flooding tool. The full source code is maintained in a separate private repository.**

---

## About

`mfloods` is a high-performance HTTP request flooding tool written in Rust, designed for load testing and stress testing web applications.

- 🚀 **High Performance**: Built with Rust for maximum speed and efficiency
- 🔄 **Parallel Processing**: Configurable multi-threading for concurrent requests
- 🌐 **Proxy Support**: HTTP, HTTPS, and SOCKS5 proxy support
- 🔒 **SSL Options**: Configurable SSL certificate verification
- 📊 **Progress Tracking**: Real-time progress bar for large request batches
- 📝 **Flexible Input**: Raw HTTP request files for complete control
- 🎯 **Connection Pooling**: Efficient connection management to prevent resource exhaustion
- 📈 **Detailed Logging**: Multiple log levels for debugging and monitoring

---

## Project Structure & Source Code

- **This repository (`mfloods`)**: Contains only the compiled binaries (in the `release/` directory) and documentation for public distribution.
- **Source code repository (`mfloods-src`)**: The full Rust source code is maintained in a separate, private repository. If you are interested in contributing or reviewing the source, please contact the maintainer.

> **Note:** The source code is not included here for distribution purposes. This split helps keep the public release focused on easy-to-use binaries, while development and contributions are managed privately.

---

## Quick Start

### Download

Download the latest release for your platform from the [Releases](https://github.com/insomn14/mfloods/releases) page.

### Basic Usage

```bash
# Single request
./mfloods request.txt

# Multiple requests with threading
./mfloods -num 100 -th 4 request.txt

# With proxy
./mfloods -num 50 -th 2 -proxy http://proxy:8080 request.txt

# With SSL bypass for proxy
./mfloods -insecure -proxy http://127.0.0.1:8080 request.txt
```

---

## Command Line Options

| Option | Description | Default |
|--------|-------------|---------|
| `-h, --help` | Show help message | - |
| `-log <level>` | Set log level (error, warn, info, debug, trace) | info |
| `-num <count>` | Number of requests to make | 1 |
| `-th <threads>` | Number of threads for parallel processing | 1 |
| `-proxy <url>` | Proxy URL (http://, https://, socks5://) | none |
| `-insecure` | Disable SSL certificate verification | false |

## Log Levels

- **error**: Only error messages
- **warn**: Warnings and errors
- **info**: Important information with progress bar (default)
- **debug**: Detailed information including headers
- **trace**: Most detailed information

## HTTP Request File Format

Create a text file containing a raw HTTP request:

```
POST /api/endpoint HTTP/2
Host: example.com
User-Agent: mfloods/1.0
Content-Type: application/json
Accept: */*
Connection: keep-alive

{"key": "value"}
```

---

## Use Cases

### Load Testing
```bash
# Test with 1000 requests using 8 threads
./mfloods -num 1000 -th 8 -log info request.txt
```

### Proxy Testing
```bash
# Test through HTTP proxy
./mfloods -num 100 -th 4 -proxy http://127.0.0.1:8080 request.txt

# Test through SOCKS5 proxy
./mfloods -num 100 -th 4 -proxy socks5://127.0.0.1:9050 request.txt
```

### SSL/Proxy Scenarios
```bash
# Bypass SSL verification for proxy testing
./mfloods -insecure -proxy http://127.0.0.1:8080 request.txt
```

---

## Performance Features

- **Connection Pooling**: Reuses connections to reduce overhead
- **Resource Management**: Automatic cleanup of idle connections
- **Concurrency Control**: Limits concurrent connections to prevent resource exhaustion
- **Timeout Protection**: Prevents hanging requests from consuming resources

---

## Security Notice

⚠️ **Warning**: This tool is designed for testing and debugging purposes only. Use responsibly and only on systems you own or have explicit permission to test.

- The `-insecure` flag disables SSL security - use only in trusted environments
- Always respect rate limits and terms of service
- Do not use for malicious purposes

---

## Building from Source

> **Source code is not included in this repository.**
>
> If you wish to build from source, please refer to the private development repository or contact the maintainer for access.

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Contributing

For source code contributions, please refer to the main development repository. This repository does not accept code contributions.

---

## Support

For issues, questions, or feature requests, please open an issue on GitHub.

---

## Buy Me a Coffee ☕

If you find this tool useful and would like to support its development, consider buying me a coffee!

**Bitcoin Address:**
```
bitcoin:1c5ANBcxzs5HK5daQ3C7nYbvSwVbQvdh5
```

Your support helps keep this project maintained and improved. Thank you! 🙏 
