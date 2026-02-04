# AI ChatBot with Dual CNN & Web Research

An intelligent AI-powered chatbot featuring **dual CNN image classification** and **web research integration**. Combines ResNet50 and EfficientNet-B0 models with real-time web search to provide comprehensive, educational responses about uploaded images.

## 🚀 Features

### **Core Capabilities**
- 🔍 **Dual CNN Classification** - ResNet50 + EfficientNet-B0 for accurate image recognition
- 🌐 **Web Research Integration** - Real-time information gathering from the internet
- 🤖 **AI-Powered Analysis** - Groq LLM synthesizes technical results into engaging content
- 📚 **Educational Responses** - User-friendly paragraphs with habitat, diet, behavior, and fun facts
- 🧹 **Enhanced Cache Clearing** - Automatic cleanup prevents image persistence between queries

### **User Experience**
- 💬 **Real-time Chat** - Streamlit-based interactive interface
- 🌍 **Multi-language Support** - Responses in multiple languages
- 📱 **Responsive Design** - Works on desktop and mobile devices
- ⏰ **Real-time Data** - Includes current date/time and weather information
- 🎯 **No Technical Jargon** - Clean, confidence-free responses focused on education

## 🛠️ Quick Start

### 1. Prerequisites
```bash
# Python 3.8+ required
python --version

# Install dependencies
pip install -r requirements.txt
```

### 2. Environment Setup
Create a `.env` file with your API keys:
```env
GROQ_API_KEY=your_groq_api_key_here
# Optional: Add other API keys for enhanced features
GOOGLE_API_KEY=your_google_api_key_here
OPENAI_API_KEY=your_openai_api_key_here
```

### 3. Run the Application
```bash
# Option 1: Direct run
streamlit run app_ui.py

# Option 2: Using run script
python run_app.py

# Option 3: Test first, then run
python test_app.py
python run_app.py
```

### 4. Access the Application
- Open your browser to: `http://localhost:8501`
- Toggle **CNN Mode** to enable image analysis
- Upload images and ask questions!

## 📋 System Requirements

### **Minimum Requirements**
- **RAM**: 8GB+ (for TensorFlow models)
- **Storage**: 5GB+ (for CNN models and dependencies)
- **Python**: 3.8 or higher
- **Internet**: Required for web research and model downloads

### **Recommended**
- **RAM**: 16GB+ for optimal performance
- **GPU**: CUDA-compatible GPU for faster CNN inference
- **SSD**: For faster model loading

## 🔧 Configuration

### **API Keys (Required)**
- **GROQ_API_KEY**: For text generation and synthesis
- **GOOGLE_API_KEY**: (Optional) For enhanced features
- **OPENAI_API_KEY**: (Optional) For backup capabilities

### **Supported Image Formats**
- PNG, JPG, JPEG, GIF, BMP, WEBP
- Maximum recommended size: 10MB
- Optimal resolution: 224x224 to 1024x1024 pixels

## 🎯 How It Works

### **Image Analysis Pipeline**
1. **Upload & Validation** → Image format and size validation
2. **CNN Classification** → ResNet50 and EfficientNet-B0 analysis
3. **Object Identification** → Primary object extraction from results
4. **Web Research** → Multi-query information gathering via DuckDuckGo API
5. **AI Synthesis** → Groq LLM combines technical data with web research
6. **User Response** → Educational paragraphs with emojis and clear sections
7. **Cache Clearing** → Automatic cleanup prevents image persistence

### **Response Format**
```
🔍 What I See:
Clear identification and description of the object...

🌍 Where It's From:
Natural habitat and geographic distribution...

🍽️ Diet & Feeding:
Feeding habits and dietary preferences...

✨ Notable Features:
Distinctive characteristics and adaptations...

🎭 Behavior & Lifestyle:
Typical behaviors and social patterns...

🤓 Fun Facts:
Interesting and educational information...
```

## 📁 Project Structure

```
├── app_ui.py                 # Main application (Streamlit GUI + CNN + Web Research)
├── requirements.txt          # Python dependencies
├── .env                     # Environment variables (API keys)
├── run_app.py               # Simple run script
├── test_app.py              # Dependency and functionality tests
├── test_no_confidence.py    # Confidence removal verification
└── README.md                # This file
```

## 🧪 Testing

### **Run Tests**
```bash
# Test all dependencies and functionality
python test_app.py

# Verify confidence percentages are removed
python test_no_confidence.py

# Test specific components
python -c "import tensorflow as tf; print('TensorFlow:', tf.__version__)"
python -c "import streamlit as st; print('Streamlit installed successfully')"
```

### **Expected Test Results**
- ✅ All imports successful
- ✅ TensorFlow models load correctly
- ✅ API keys configured properly
- ✅ No confidence percentages in output
- ✅ User-friendly format elements present

## 🔍 Usage Examples

### **Text Chat**
1. Keep CNN Mode **OFF**
2. Type questions about general topics
3. Get real-time aware responses with current data

### **Image Analysis**
1. Toggle **CNN Mode ON**
2. Upload an image (PNG, JPG, etc.)
3. Ask questions like:
   - "What is this animal?"
   - "Where does it live?"
   - "What does it eat?"
   - "Tell me interesting facts about it"

### **Multi-language Support**
- Select your preferred language from the sidebar
- All responses will be generated in the chosen language
- Supports: English, Spanish, French, German, Chinese, Japanese

## 🛠️ Troubleshooting

### **Common Issues**

#### **TensorFlow Installation**
```bash
# If TensorFlow fails to install
pip install --upgrade pip
pip install tensorflow==2.13.0

# For Apple Silicon Macs
pip install tensorflow-macos tensorflow-metal
```

#### **Model Loading Errors**
```bash
# Clear TensorFlow cache
rm -rf ~/.keras/models/

# Reinstall with specific version
pip uninstall tensorflow
pip install tensorflow==2.13.0
```

#### **Streamlit Issues**
```bash
# Clear Streamlit cache
streamlit cache clear

# Reset Streamlit config
rm -rf ~/.streamlit/
```

#### **API Key Problems**
- Verify `.env` file exists in project root
- Check API key format (no quotes needed)
- Ensure GROQ_API_KEY is valid and active
- Test API connection: `curl -H "Authorization: Bearer YOUR_KEY" https://api.groq.com/openai/v1/models`

### **Performance Optimization**
- **Slow CNN inference**: Consider using GPU acceleration
- **High memory usage**: Close other applications, use smaller batch sizes
- **Slow web research**: Check internet connection, try different queries

## 🔄 Updates & Maintenance

### **Model Updates**
- CNN models auto-download on first run
- Web research uses live APIs (always current)
- Groq API provides latest language model capabilities

### **Dependency Updates**
```bash
# Update all packages
pip install --upgrade -r requirements.txt

# Update specific packages
pip install --upgrade streamlit tensorflow
```

## 🤝 Contributing

### **Development Setup**
```bash
# Clone repository
git clone <repository-url>
cd ai-chatbot-cnn

# Install in development mode
pip install -r requirements.txt

# Run tests
python test_app.py

# Start development server
streamlit run app_ui.py
```

### **Code Structure**
- **app_ui.py**: Main application with GUI, CNN processing, and web research
- **Modular functions**: Each feature is separated into clear functions
- **Error handling**: Comprehensive error handling and user feedback
- **Cache management**: Automatic cleanup prevents memory issues

## 📄 License

MIT License - Feel free to modify and use for your projects.

## 🙏 Acknowledgments

- **TensorFlow/Keras**: For ResNet50 and EfficientNet-B0 models
- **Streamlit**: For the interactive web interface
- **Groq**: For fast and reliable language model API
- **DuckDuckGo**: For web search capabilities
- **ImageNet**: For pre-trained model weights

---

**Built with ❤️ for educational and research purposes**