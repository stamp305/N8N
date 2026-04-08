# Contributing to AI Diagram to n8n Workflow Converter

Thank you for your interest in contributing! This document will guide you through the contribution process.

## Getting Started

1. Fork the repository
2. Clone your forked repository
3. Create a new branch for your feature: `git checkout -b feature/your-feature-name`

## Development Setup

```bash
# Create virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies including dev tools
pip install -r requirements.txt

# Run the application
python app.py
```

## Code Style Guidelines

- Follow PEP 8 Python style guide
- Use meaningful variable and function names
- Add docstrings to functions and classes
- Keep functions focused and modular
- Comment complex logic

Example:
```python
def validate_and_fix_workflow(self, workflow: dict) -> dict:
    """
    Validates and fixes n8n workflow structure for compatibility.
    
    Args:
        workflow: Dictionary containing n8n workflow data
        
    Returns:
        Fixed workflow dictionary
    """
    # Implementation
    return workflow
```

## Submitting Changes

1. **Commit your changes** with clear, descriptive messages:
   ```bash
   git commit -m "Fix: resolve issue with node type normalization"
   git commit -m "Feature: add support for new n8n node type"
   ```

2. **Push to your fork**:
   ```bash
   git push origin feature/your-feature-name
   ```

3. **Open a Pull Request** with:
   - Clear description of changes
   - Reference to related issues (if any)
   - Test results or screenshots (if applicable)

## Types of Contributions

### Bug Fixes
- Include steps to reproduce
- Explain expected vs actual behavior
- Test thoroughly before submitting

### New Features
- Discuss in an issue first for major features
- Keep changes focused and modular
- Update README if it affects user-facing functionality
- Add appropriate error handling

### Documentation
- Fix typos, clarify unclear sections
- Add examples for complex features
- Update API documentation if relevant

## Testing

While we don't have automated tests yet, please:
- Test your changes manually with various flowchart diagrams
- Verify the generated workflows are valid in n8n
- Test edge cases (empty diagrams, large images, etc.)
- Check error handling for missing dependencies

## Common Issues

### "ModuleNotFoundError" when running
- Ensure virtual environment is activated
- Run `pip install -r requirements.txt` again

### Ollama connection fails
- Verify Ollama is running: `ollama serve`
- Check OLLAMA_BASE_URL in .env
- Ensure models are pulled: `ollama pull llava:13b`

### Changes to app.py not reflected
- Restart the application completely
- Clear any Python cache: `find . -type d -name __pycache__ -delete`

## Questions?

- Create an issue with the `question` label
- Check existing issues and discussions
- Review the main README for troubleshooting section

## Recognition

Contributors will be recognized in the README and commit history. Thank you for making this project better!
