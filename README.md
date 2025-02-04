MERN 스택 초기 세팅 가이드

📌 사용한 버전
MACBOOK-air-m2<br>
Node.js: v22.13.1<br>

npm: 10.9.2<br>
```
FrontEnd
{username}-ui-MacBookAir frontend % npm list react
frontend@0.1.0 /Users/{username}/Documents/project/mern01/frontend
├─┬ react-dom@19.0.0
│ └── react@19.0.0 deduped
├─┬ react-scripts@5.0.1
│ └── react@19.0.0 deduped
└── react@19.0.0
```

```
BackEnd
{username}-ui-MacBookAir backend % npm list express
backend@1.0.0 /Users/{username}/Documents/project/mern01/backend
└── express@4.21.2
```

```
MongoDB
{username}-ui-MacBookAir backend % mongod --version
db version v7.0.16
Build Info: {
    "version": "7.0.16",
    "gitVersion": "18b949444cfdaa88e30b0e10243bc18268251c1f",
    "modules": [],
    "allocator": "system",
    "environment": {
        "distarch": "aarch64",
        "target_arch": "aarch64"
    }
}
```

```
Mongoose
{username}-ui-MacBookAir backend % npm list mongoose   
backend@1.0.0 /Users/catsea/Documents/project/mern01/backend
└── mongoose@8.9.6
```

🛠 MERN 스택 프로젝트 초기 세팅

1️⃣ 프로젝트 폴더 생성
```
mkdir mern-project && cd mern-project
```
2️⃣ 백엔드(Node.js + Express) 설정
```
mkdir backend && cd backend
npm init -y
```
📌 Express, Mongoose, CORS 등 필수 패키지 설치
```
npm install express mongoose dotenv cors body-parser
```
📌 개발 시 편의를 위한 추가 패키지 설치
```
npm install --save-dev nodemon
```
📌 backend/server.js 파일 생성 후 기본 서버 코드 추가
```
const express = require("express");
const mongoose = require("mongoose");
const cors = require("cors");
const dotenv = require("dotenv");

dotenv.config();
const app = express();
app.use(express.json());
app.use(cors());

const PORT = process.env.PORT || 5000;
app.listen(PORT, () => console.log(`Server running on port ${PORT}`));
```

📌 nodemon을 사용해 서버 실행 (backend/package.json 수정)
```
"scripts": {
  "start": "node server.js",
  "dev": "nodemon server.js"
}
```

서버 실행:
```
npm run dev
```
3️⃣ 프론트엔드(React) 설정
```
cd ..
npx create-react-app frontend --use-npm
cd frontend
```

📌 React 필수 패키지 설치
```
npm install axios react-router-dom
```
📌 frontend/src/App.js 기본 코드
```
import React from "react";
function App() {
  return <h1>Welcome to MERN Stack</h1>;
}
export default App;
```
React 실행:
```
npm start
```
