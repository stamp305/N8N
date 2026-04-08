# AI Diagram to n8n Workflow Converter

A sophisticated desktop application that converts flowchart diagrams and images into automated n8n workflows using AI vision and language models.

## 🎯 Features

- **Image Analysis**: Leverages LLaVA vision model to analyze flowchart diagrams
- **AI-Powered Logic Refinement**: Uses Phi-3 and DeepSeek models to interpret flowchart logic
- **Automatic n8n Workflow Generation**: Converts diagrams directly into valid n8n JSON workflows
- **OCR Support**: Integrates EasyOCR and Tesseract for text extraction from images
- **Google Cloud Vision Integration**: Optional advanced image recognition capability
- **n8n API Integration**: Direct workflow upload and activation to n8n instances
- **Interactive GUI**: Modern CustomTkinter-based interface with real-time feedback
- **Workflow Validation**: Comprehensive validation and auto-fixing for n8n compatibility

## 📋 Tech Stack

- **Python 3.8+**
- **GUI Framework**: CustomTkinter
- **AI Models**: 
  - LLaVA (vision)
  - Phi-3 (reasoning)
  - DeepSeek-Coder (JSON generation)
- **Image Processing**: PIL, EasyOCR, Tesseract
- **API Clients**: Google Cloud Vision, n8n API
- **Automation Platform**: n8n (requires local/remote instance)

## 🚀 Installation

### Prerequisites
- Python 3.8 or higher
- [Ollama](https://ollama.ai) installed and running (for local AI models)
- Optional: Google Cloud Vision credentials
- Optional: n8n instance (local or remote)

### Setup Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/ai-diagram-to-n8n-workflow.git
   cd ai-diagram-to-n8n-workflow
   ```

2. **Create virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Configure environment variables**
   ```bash
   cp .env.example .env
   # Edit .env with your settings:
   #   N8N_BASE_URL: Your n8n instance URL (default: http://localhost:5678)
   #   N8N_API_KEY: Your n8n API key (optional)
   #   GOOGLE_APPLICATION_CREDENTIALS: Path to Google Cloud credentials (optional)
   ```

5. **Ensure Ollama is running**
   ```bash
   ollama serve
   ```
   In another terminal, pull required models:
   ```bash
   ollama pull llava:13b
   ollama pull deepseek-coder:6.7b
   ollama pull phi:latest
   ```

6. **Run the application**
   ```bash
   python app.py
   ```

## 💡 Usage

1. **Upload Flowchart Image**
   - Click "Select Image" and choose your flowchart diagram
   - Supports PNG, JPG, JPEG formats
   - Recommended minimum size: 800x800 pixels

2. **Configure AI Models**
   - Select preferred Ollama models in the Config tab
   - Test connections to Ollama and n8n instances

3. **Generate Workflow**
   - Add optional notes about the diagram in the "User Notes" field
   - Click "Generate Workflow"
   - Watch real-time progress in the message log

4. **Review & Export**
   - View generated workflow JSON in the Output tab
   - Download as JSON file or copy to clipboard
   - Upload directly to n8n instance (with API key configured)

## 📊 Workflow Generation Process

```
Flowchart Image
    ↓
Vision Analysis (LLaVA)
    ↓
Logic Refinement (Phi-3)
    ↓
n8n JSON Generation (DeepSeek-Coder)
    ↓
Validation & Auto-fix
    ↓
Valid n8n Workflow JSON
```

## 🔧 Configuration

### Available Ollama Models
- `llava:13b` - Vision analysis (recommended)
- `deepseek-coder:6.7b` - JSON code generation
- `deepseek-r1:7b` - Reasoning and logic
- `phi:latest` - Lightweight reasoning
- `llama2:latest` - General purpose

### Supported n8n Node Types
The application supports:
- Triggers: Manual, Webhook, Cron
- Logic: IF, Switch, Code
- Data: Set, Merge, SplitInBatches
- Integrations: HTTP Request, OpenAI, Google Sheets, Notion
- And 15+ more node types

## 🔒 Security

- **Never commit `.env` file** - Credentials are in .gitignore
- API keys are loaded from environment variables only
- Use `.env.example` as template for your configuration

## 📝 Example

```python
# Create app instance
app = DiagramToN8nApp()

# Process flowchart image
workflow = app.flowchart_to_n8n_workflow()

# Upload to n8n (with API key configured)
app.upload_workflow_to_n8n()
```

## 🐛 Troubleshooting

### "Connection to Ollama failed"
- Ensure Ollama is running: `ollama serve`
- Check Ollama URL in Config tab (default: http://localhost:11434)
- Pull required models: `ollama pull llava:13b`

### "Image too small"
- Flowcharts should be at least 800x800 pixels
- Higher resolution images improve accuracy

### "Invalid n8n workflow generated"
- Check n8n instance version compatibility
- Review generated JSON in Output tab
- Try with different Ollama models

### "Google Vision API errors"
- Verify credentials file path in .env
- Ensure credentials have necessary Vision API permissions

## 📈 Performance Tips

1. Use LLaVA for vision tasks (most accurate)
2. Use DeepSeek-Coder for JSON generation (creates valid n8n syntax)
3. Keep flowchart diagrams clean and well-labeled
4. Provide clear user notes for complex workflows
5. Test with smaller diagrams first

## 🤝 Contributing

Contributions are welcome! Please:
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see LICENSE file for details.

## 👤 Author

Created and maintained as an AI automation portfolio project.

## 🙏 Acknowledgments

- [n8n](https://n8n.io) - Workflow automation platform
- [Ollama](https://ollama.ai) - Local AI model runtime
- [CustomTkinter](https://github.com/TomSchimansky/CustomTkinter) - Modern GUI framework
- Open source community for excellent libraries

## 📞 Support

For issues, questions, or suggestions:
- Open an issue on GitHub
- Check existing documentation
- Review the troubleshooting section

---

**Last Updated**: 2026  
**Status**: Active Development
