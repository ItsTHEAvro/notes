# Avro's Notes

A personal knowledge base and documentation site built with MkDocs, featuring notes on academic topics, programming tutorials, Kaggle competitions, and more.

## 🌐 Live Site

Visit the live site at: [Avro's Notes](https://itstheavro.github.io/notes/)

## 📁 Project Structure

```
.
├── README.md
├── mkdocs.yml              # MkDocs configuration
├── docs/                   # Documentation source files
│   ├── index.md           # Home page
│   ├── about.md           # About page
│   ├── academic/          # Academic notes
│   │   └── index.md
|   |
│   ├── kaggle/            # Kaggle competition notes
│   │   └── index.md
|   |
│   ├── programming/       # Programming tutorials
│   │   └── index.md
│   │   
│   ├── misc/              # Miscellaneous notes
│   ├── assets/            # Images and media
│   ├── javascripts/       # Custom JavaScript (MathJax)
│   └── stylesheets/       # Custom CSS
├── site/                  # Generated static site
├── venv-for-blog/         # Python virtual environment
└── .github/
    └── workflows/
        └── ci.yaml        # GitHub Actions CI/CD
```

## 🚀 Quick Start

### Prerequisites

- Python 3.7 or higher
- pip (Python package installer)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/ItsTHEAvro/notes
   cd blog-project
   ```

2. **Create and activate virtual environment**
   ```bash
   python -m venv venv-for-blog
   
   # On Windows
   venv-for-blog\Scripts\activate
   
   # On macOS/Linux
   source venv-for-blog/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install mkdocs mkdocs-material
   ```

### Development

1. **Start the development server**
   ```bash
   mkdocs serve
   ```
   
2. **Open your browser**
   Navigate to `http://localhost:8000` to view the site

3. **Live reload**
   The site automatically reloads when you make changes to the documentation files

### Building for Production

```bash
mkdocs build
```

This generates the static site in the `site/` directory.

## 📝 Content Categories

### 📚 Academic Notes
- Notes on academic subjects


### 💻 Programming
- Various pogramming concepts

### 🏆 Kaggle Competitions
- Competition insights and analysis
- Machine learning approaches and solutions

### 📋 Miscellaneous
- Various topics and general notes

## 🛠️ Features

- **Responsive Design**: Mobile-friendly documentation
- **Math Support**: MathJax integration for mathematical expressions
- **Code Highlighting**: Syntax highlighting for multiple programming languages
- **Search**: Full-text search functionality
- **Dark/Light Theme**: Toggle between themes
- **CI/CD**: Automated deployment with GitHub Actions

## 🎨 Customization

The site uses custom styling defined in [`docs/stylesheets/extra.css`](docs/stylesheets/extra.css), including:
- Enhanced blockquotes
- Custom note cards
- Dark mode adjustments
- Hover effects and transitions

## 🚀 Deployment

The site is automatically deployed using GitHub Actions. The workflow is defined in [`.github/workflows/ci.yaml`](.github/workflows/ci.yaml).

### Manual Deployment

To deploy manually:

1. Build the site: `mkdocs build`
2. Deploy the contents of the `site/` directory to your web server

## 🤝 Contributing

This is a personal knowledge base, but if you find errors or have suggestions:

1. Open an issue to discuss the change
2. Fork the repository
3. Create a feature branch
4. Make your changes
5. Submit a pull request

## 📬 Contact

- **GitHub**: [ItsTHEAvro](https://github.com/ItsTHEAvro)
- **LinkedIn**: [Jyotirmoy Avro](https://linkedin.com/in/jyotirmoy-avro)

## 📄 License

This project is open source. Feel free to use the structure and code for your own documentation projects.

---

**Note**: This is a personal knowledge base. Content reflects my learning journey and may contain subjective interpretations or work-in-progress notes.