# Helm Charts

A central repository for Helm charts maintained by kayaman.

## Available Charts

This repository contains the following Helm charts:

### 1. Parrot
A modern, production-ready HTTP echo server that parrots back comprehensive request information. Perfect for debugging webhooks, testing HTTP clients, monitoring network requests, and understanding API interactions.

**Repository:** [kayaman/parrot](https://github.com/kayaman/parrot)

### 2. STT Audio Preprocess
A high-performance, containerized service for preprocessing audio files before speech-to-text (STT) processing. Optimized for Whisper and similar services with features like VAD, silence compression, and noise reduction.

**Repository:** [kayaman/stt-audio-preprocess](https://github.com/kayaman/stt-audio-preprocess)

### 3. Audio Transcription Player
A professional web application for playing audio files with synchronized transcription text highlighting. Built with Next.js 14, TypeScript, and Tailwind CSS.

**Repository:** [kayaman/audio-transcription-player](https://github.com/kayaman/audio-transcription-player)

### 4. Lylics
A lightweight Rust microservice that streams random lyrics chunks via Server-Sent Events (SSE).

**Repository:** [kayaman/lylics](https://github.com/kayaman/lylics)

## Usage

### Prerequisites

- Kubernetes cluster (v1.19+)
- Helm 3.x

### Installing a Chart

To install a chart from this repository:

```bash
# Clone the repository
git clone https://github.com/kayaman/helm-charts.git
cd helm-charts

# Install a chart (example: parrot)
helm install my-parrot ./charts/parrot

# Install with custom values
helm install my-parrot ./charts/parrot -f custom-values.yaml

# Install a specific chart version
helm install my-parrot ./charts/parrot --version 1.1.0

# Install lylics with custom lyrics data
helm install lylics ./charts/lylics --set lyricsData='["hello world","another lyric"]'
```

### Upgrading a Chart

```bash
helm upgrade my-parrot ./charts/parrot
```

### Uninstalling a Chart

```bash
helm uninstall my-parrot
```

### Viewing Chart Values

```bash
# View default values for a chart
helm show values ./charts/parrot

# View all chart information
helm show all ./charts/parrot
```

## Chart Structure

Each chart follows the standard Helm chart structure:

```
charts/
├── <chart-name>/
│   ├── Chart.yaml              # Chart metadata
│   ├── values.yaml             # Default configuration values
│   ├── values.schema.json      # JSON schema for values validation (optional)
│   ├── templates/              # Kubernetes resource templates
│   │   ├── deployment.yaml
│   │   ├── service.yaml
│   │   ├── hpa.yaml
│   │   ├── pdb.yaml
│   │   ├── _helpers.tpl        # Template helpers
│   │   └── NOTES.txt           # Post-install notes
│   └── README.md               # Chart documentation (optional)
```

## Contributing

Contributions are welcome! Please follow these guidelines:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test your changes with `helm lint`
5. Submit a pull request

## License

This repository is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

Each chart may have its own license - please check the individual chart directories for details.