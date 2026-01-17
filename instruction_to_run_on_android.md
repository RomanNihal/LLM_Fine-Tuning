# Run llama.cpp on Termux (Android)

### Prerequisite: Install Termux from F-Droid
https://f-droid.org/en/packages/com.termux/

### 1. Update your system
pkg update && pkg upgrade -y

### 2. Install build tools
pkg install git cmake clang ninja wget -y

### 3. Download the source code
git clone https://github.com/ggerganov/llama.cpp

cd llama.cpp

### 4. Configure the build
cmake -B build

### 5. Compile (heavy step – takes ~5–10 minutes)
### -j4 uses 4 CPU cores
cmake --build build --config Release -j4

### 6. Create models folder
mkdir -p models

### 7. Download Phi-3 Mini (≈2.2 GB)
wget -O models/Phi-3-mini-4k-instruct-q4.gguf https://huggingface.co/microsoft/Phi-3-mini-4k-instruct-gguf/resolve/main/Phi-3-mini-4k-instruct-q4.gguf

### 8. Run the model
./build/bin/llama-cli -m models/Phi-3-mini-4k-instruct-q4.gguf -n 400


# ---- Using your own fine-tuned model ----

### 1. Grant Termux storage permission first
termux-setup-storage

### 2. Place your model in the Android Download folder, then run:
cp /sdcard/Download/model_name.gguf ~/llama.cpp/models/

### 3. Run your fine-tuned model
cd llama.cpp

./build/bin/llama-cli -m models/model_name.gguf -n 200