# Policy-scanner
- Takes the pdf of an updated policy and tells whether it affects a respective company or not.
- Useful for companies to track if an update on policy affects them or not, and if yes then how it affects the company.
- Made using OpenAI's GPT 3.5 API.

## FLowchart explaination 
```mermaid
graph LR;

subgraph User
    A[User]
    A --> B[Upload PDF / Enter Text]
    B --> C[Submit]
end

subgraph Web Application
    C --> D{Request Method}
    D --> |POST| E[Extract Text]
    D --> |POST| F[Construct Prompt]
    F --> G[Call GPT-3 API]
    G --> H[Retrieve Response]
    H --> I[Display Result]
    I --> J{Repeat?}
    J --> |Yes| B
    J --> |No| End[End]
end

subgraph PDF Processing
    E --> K[PDF Text Extraction]
    K --> L[Text Data]
end

subgraph GPT-3 API
    F --> M[API Request]
    M --> N[GPT-3 Engine]
    N --> O{Generate Text}
    O --> P[API Response]
end
```

## Dependencies 
```
OpenAI
Flask
PyPDF2
```

## Installation
```
1. pip install required libraries
2. connect your OpenAI API Key
3. run the flask app
4. results on port 5000 (http://127.0.0.1:5000)
```
