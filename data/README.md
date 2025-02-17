# How to download a dataset for a Kaggle competition

### **1. Install the Kaggle API**
If you haven't installed the Kaggle API yet, do so using pip:

```bash
pip install kaggle
```

### **2. Authenticate with Kaggle**
You need a Kaggle API key to authenticate.

1. Go to [Kaggle](https://www.kaggle.com/).
2. Click on your **profile picture** (top right) → **Account**.
3. Scroll down to the **API** section and click **Create New API Token**.
4. A `kaggle.json` file will be downloaded.
5. Move the `kaggle.json` file to `~/.kaggle/` (Linux/macOS) or `%USERPROFILE%\.kaggle\` (Windows).

```bash
mkdir -p ~/.kaggle
mv ~/Downloads/kaggle.json ~/.kaggle/
chmod 600 ~/.kaggle/kaggle.json  # Set correct permissions
```

### **3. List Available Competitions**
To check the competitions you have access to:

```bash
kaggle competitions list
```

### **4. Download the Competition Dataset**
Replace `<competition-name>` with the actual competition name (found from `kaggle competitions list`):

```bash
kaggle competitions download -c <competition-name>
```

For example, if the competition is "titanic":

```bash
kaggle competitions download -c titanic
```

This will download a ZIP file containing the dataset.

### **5. Extract the Dataset**
Once downloaded, unzip the dataset:

```bash
unzip titanic.zip -d titanic_data/
```

For Windows:

```powershell
Expand-Archive titanic.zip -DestinationPath titanic_data
```

### **6. Alternative: Download Specific Files**
If you only need specific files:

```bash
kaggle competitions download -c <competition-name> -f <file-name>
```

For example:

```bash
kaggle competitions download -c titanic -f train.csv
```
