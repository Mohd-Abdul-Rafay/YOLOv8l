# Contributing Guidelines

Thank you for your interest in contributing to **YOLOv8l Baseline — VisDrone**!  
Please follow these guidelines to keep contributions clear and consistent.

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

## 🐛 Reporting Issues
- Use the GitHub [Issues](../../issues) tab.
- Provide a clear description, steps to reproduce, and expected vs. actual behavior.
- Include environment details (OS, Python, Torch, Ultralytics versions; Colab/Local).

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

## 💡 Feature Requests
- Open an issue and tag it as a *feature request*.
- Explain the motivation, scope, and links to references if available.

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

## 🔧 Pull Requests
1. Fork the repository and create a branch:
   ```bash
   git checkout -b feature/my-feature
   ```
2. Make your changes (do not break existing paths or notebook flow).
3. Ensure notebooks/scripts run without errors.
4. Commit and push:
   ```bash
   git commit -m "Add my new feature"
   git push origin feature/my-feature
   ```
5. Open a Pull Request (PR) against the main branch with a clear summary of changes.

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

## 📏 Code Style
	•	Follow PEP8￼ for Python.
	•	Keep notebooks tidy: remove unnecessary outputs before committing.
	•	Track large binaries (weights, ONNX, TorchScript, etc.) with Git LFS.

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

## ✅ Testing
	•	Verify that training and inference cells in the notebook execute end-to-end.
	•	If adding configs or scripts, include a minimal usage example in the PR.

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

## 🔐 Secrets & Data
	•	Do not commit credentials, API keys, or private dataset files.
	•	Datasets should be referenced via links or documented download steps (e.g., KaggleHub).

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

## 🙏 Acknowledgement

By contributing, you agree that your contributions will be licensed under the MIT License of this repository.
