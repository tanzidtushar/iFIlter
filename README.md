# iFilter – Serverless AI Image Analyzer

A serverless, low-latency cloud-native web application that leverages AWS AI services to analyze images using multiple Amazon Rekognition detection modes. Built as a capstone project for MINT 709 at the University of Alberta.

---

## 🚀 Features

- 📸 Upload images directly through the web interface
- 🤖 AI-powered image analysis via Amazon Rekognition
- 🔐 Secure user authentication with Amazon Cognito
- ☁️ Scalable serverless architecture — no server management required
- 🧠 Multiple Rekognition analysis modes:
  - **Label Detection** – Identifies objects, scenes, and concepts
  - **Face Analysis** – Detects faces and attributes
  - **Content Moderation** – Flags inappropriate content
  - **Text Detection** – Extracts text from images

---

## 🏗️ Architecture

```
User → Amazon Cognito (Auth) → Web App (S3 Static Hosting)
                                      ↓
                              AWS Lambda (Node.js)
                                      ↓
                        Amazon Rekognition (AI Inference)
                                      ↓
                          Amazon S3 (Image Storage)
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | JavaScript (ES6+) |
| Runtime | Node.js, AWS Lambda |
| Authentication | Amazon Cognito |
| AI Inference | Amazon Rekognition |
| Storage | Amazon S3 |
| SDK | AWS SDK for JavaScript |

---

## ⚙️ Prerequisites

- [Node.js](https://nodejs.org/) v18+
- [AWS CLI](https://aws.amazon.com/cli/) configured with appropriate credentials
- An AWS account with access to Lambda, S3, Cognito, and Rekognition

---

## 🔧 Setup & Deployment

1. **Clone the repository**
   ```bash
   git clone https://github.com/tanzidtushar/iFIlter.git
   cd iFIlter
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Configure AWS credentials**
   ```bash
   aws configure
   ```

4. **Set up environment variables**
   Create a `.env` file in the root directory:
   ```env
   AWS_REGION=your-region
   S3_BUCKET_NAME=your-bucket-name
   COGNITO_USER_POOL_ID=your-user-pool-id
   COGNITO_CLIENT_ID=your-client-id
   ```

5. **Deploy Lambda functions**
   ```bash
   npm run deploy
   ```

6. **Launch the app**
   Open `index.html` in your browser or deploy the frontend to an S3 static website.

---

## 📁 Project Structure

```
iFIlter/
├── src/
│   ├── lambda/          # AWS Lambda function handlers
│   ├── auth/            # Cognito authentication logic
│   └── rekognition/     # Rekognition API integration
├── public/
│   ├── index.html       # Main web interface
│   └── assets/          # Static assets
├── .env.example
├── package.json
└── README.md
```

---

## 🔒 Security

- All users must authenticate via **Amazon Cognito** before accessing the application
- Images are stored securely in **Amazon S3** with access controlled via IAM policies
- **JWT tokens** are used for session management
- AWS **IAM roles** follow the principle of least privilege

---

## 📚 Course

**MINT 709 – Machine Learning for Cloud Architecture**
University of Alberta – Master of Science in Internetworking
*(September 2025 – February 2026)*

---

## 👤 Author

**Tanzid Ahmed Tushar**
- LinkedIn: [in/tanzidtushar](https://www.linkedin.com/in/tanzidtushar/)
- GitHub: [@tanzidtushar](https://github.com/tanzidtushar)
