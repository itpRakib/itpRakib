<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSE Hero Animation</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            background-color: #0D1117;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            font-family: 'Fira Code', monospace;
        }
        canvas {
            position: absolute;
            top: 0;
            left: 0;
            z-index: 1;
        }
        .hero-content {
            position: relative;
            z-index: 2;
            text-align: center;
            color: #ffffff;
            background: rgba(13, 17, 23, 0.7);
            padding: 40px;
            border-radius: 15px;
            border: 1px solid #7B2CBF;
            box-shadow: 0 0 30px rgba(123, 44, 191, 0.5);
            backdrop-filter: blur(5px);
        }
        h1 {
            font-size: 3rem;
            margin: 0 0 10px 0;
            background: linear-gradient(90deg, #9D4EDD, #E0AAFF);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        p {
            font-size: 1.2rem;
            color: #A3B3CC;
            margin: 0;
        }
    </style>
</head>
<body>

    <canvas id="techCanvas"></canvas>

    <div class="hero-content">
        <h1>MD. Rakibul Islam</h1>
        <p>>_ Software Engineer & Tech Innovator</p>
    </div>

    <script>
        const canvas = document.getElementById('techCanvas');
        const ctx = canvas.getContext('2d');

        // Set canvas to full window size
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;

        // CSE / Stack specific characters for the animation
        const chars = '01{}[]<>C++PythonSQLReactNodeJSUIUXData0101';
        const charArray = chars.split('');

        const fontSize = 16;
        const columns = canvas.width / fontSize;
        const drops = [];

        // Initialize drop positions
        for (let x = 0; x < columns; x++) {
            drops[x] = 1;
        }

        function drawMatrix() {
            // Semi-transparent black to create the trail effect
            ctx.fillStyle = 'rgba(13, 17, 23, 0.05)';
            ctx.fillRect(0, 0, canvas.width, canvas.height);

            // Dark luxury purple text color
            ctx.fillStyle = '#9D4EDD'; 
            ctx.font = fontSize + 'px Fira Code, monospace';

            for (let i = 0; i < drops.length; i++) {
                // Pick a random character
                const text = charArray[Math.floor(Math.random() * charArray.length)];
                
                // Draw the character
                ctx.fillText(text, i * fontSize, drops[i] * fontSize);

                // Reset drop to top randomly to create staggered falling effect
                if (drops[i] * fontSize > canvas.height && Math.random() > 0.975) {
                    drops[i] = 0;
                }
                drops[i]++;
            }
        }

        // Loop the animation at ~30 FPS
        setInterval(drawMatrix, 33);

        // Handle window resizing
        window.addEventListener('resize', () => {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        });
    </script>
</body>
</html>



## 01. About Me

Passionate Computer Science student and aspiring Software Engineer with a primary focus on Web Development, Cloud Infrastructure, and Technical Innovation. Experienced in engineering responsive, performant, and fully accessible web solutions using modern front-end technologies and secure database architectures.

Driven by an enterprise-grade product engineering mindset, I emphasize robust logic, clean algorithms, scalable relational database designs, and seamless cloud integration. Always keen to leverage modern engineering standards to bridge the gap between complex backend systems and intuitive user interfaces.

* **Engineering Focus:** Web Application Architecture, Cloud Services, Relational Databases
* **Core Competencies:** Full-Stack Foundations, Algorithmic Optimization, Database Security
* **Open To:** Software Engineering Internships, Junior Full Stack Roles, Open-Source Collaborations

---

## 02. Tech Stack

<div align="center">

### Languages & Core
<img src="https://skillicons.dev/icons?i=c,cpp,html,css,js,ts&theme=dark" alt="Languages" />

<br/>

### Frontend Development
<img src="https://skillicons.dev/icons?i=html,css,js,bootstrap,tailwind,react&theme=dark" alt="Frontend" />

<br/>

### Backend & Databases
<img src="https://skillicons.dev/icons?i=mysql,postgres,aws,express,nodejs&theme=dark" alt="Backend and Databases" />

<br/>

### Cloud, DevOps & Tooling
<img src="https://skillicons.dev/icons?i=aws,linux,ubuntu,git,github,vscode&theme=dark" alt="Cloud and DevOps" />

</div>

---

## 03. AI / ML Expertise

| Domain | Proficiency | Details & Applications |
| :--- | :--- | :--- |
| **Generative AI Studio** | Intermediate | Google Cloud Platform integration, Prompt Engineering, LLM Exploration |
| **Data Analysis & Processing** | Foundational | Structured data manipulation with SQL, MS Excel, and core C++ logic |
| **AI Tooling & Workflows** | Practical | Incorporating AI-assisted developer workflows for code optimization and productivity |

---

## 04. Featured Projects

<details>
<summary><b>01. Personal Portfolio & Accessibility Showcase</b> — <i>High-performance accessible web platform</i></summary>
<br/>

Engineered a fully responsive personal web platform strictly adhering to global accessibility guidelines. Optimized media assets and layout reflows to deliver exceptional visual presentation and ultra-fast page speed across desktop and mobile devices.

| Metric / Dimension | Specification / Implementation Details |
| :--- | :--- |
| **Stack** | HTML5, CSS3, Modern JavaScript, Web Accessibility Standards |
| **Scale** | Fully cross-browser compatible, zero-dependency deployment |
| **Performance** | 100% Lighthouse Accessibility & Performance Score |
| **Security** | Secure content policies, static site hardening |
| **Impact** | Serves as a reference implementation for WCAG 2.1 AA standards |
| **Repository** | [tpRakib/Portfolio](https://github.com/tpRakib) |

</details>

<details>
<summary><b>02. Relational Database Management System (RDBMS) Implementation</b> — <i>Enterprise SQL architecture</i></summary>
<br/>

Architected a robust relational database schema engineered for small-to-medium scale applications. Leveraged intermediate-to-advanced SQL techniques to manage complex relational models, constraint enforcement, and query performance optimizations.

| Metric / Dimension | Specification / Implementation Details |
| :--- | :--- |
| **Stack** | MySQL, SQL, Amazon Aurora, Amazon RDS |
| **Scale** | Multi-table relational architecture supporting high-concurrency queries |
| **Performance** | Index-optimized queries minimizing data retrieval latency |
| **Security** | Configured RDS security groups, encryption at rest, and IAM policy access |
| **Impact** | Provides high-availability database foundation with automated backups |
| **Repository** | [tpRakib/RDBMS-Implementation](https://github.com/tpRakib) |

</details>

<details>
<summary><b>03. C++ Algorithm Visualizer</b> — <i>Low-level CLI algorithm performance suite</i></summary>
<br/>

Designed a high-efficiency command-line visualization tool in C++ to demonstrate fundamental sorting and searching algorithms. Built to analyze execution time, memory overhead, and step-by-step algorithmic state shifts in real-time.

| Metric / Dimension | Specification / Implementation Details |
| :--- | :--- |
| **Stack** | C++, Data Structures & Algorithms, Standard Template Library (STL) |
| **Scale** | Command-Line Interface handling dynamic array sizes and custom input data |
| **Performance** | Native execution speed with optimized memory footprint |
| **Security** | Strict pointer and memory safety practices preventing buffer overflow |
| **Impact** | Used as an educational visual aid for peer learning in CS data structure topics |
| **Repository** | [tpRakib/CPP-Algorithm-Visualizer](https://github.com/tpRakib) |

</details>

---

## 05. Experience & Education

### **Bachelor of Applied Science (B.A.Sc.) in Computer Science**
*Northern University Bangladesh* | `Sep 2023 — May 2027`
* **Focus:** Software Engineering Principles, Data Structures & Algorithms, Database Management, Cloud Infrastructure.
* **Scope:** Developing production-grade web tools, implementing relational data models, participating in collaborative academic project builds.
* `C++` `SQL` `Web Development` `DBMS` `AWS`

### **Higher Secondary Certificate (HSC), Science**
*BAF Shaheen College Jessore* | `Graduated 2022`
* **Focus:** Higher Mathematics, Physics, Chemistry, Information & Communication Technology (ICT).
* `Mathematics` `Physics` `ICT`

---

## 06. Achievements

<div align="center">

| Recognition | Details / Field |
| :--- | :--- |
| **AWS Cloud Specialization** | Successfully completed specialized coursework in Amazon Aurora & Amazon RDS MySQL |
| **Intermediate SQL Certification** | Demonstrated mastery in complex querying, data aggregation, and database relational models |
| **Web Accessibility Leader** | Designed and showcased 100% WCAG-compliant web systems for inclusive usability |

</div>

---

## 07. Certifications

### Amazon Web Services
![](https://img.shields.io/badge/AWS-Amazon_Aurora_%26_Amazon_RDS_MySQL_Specialization-232F3E?style=flat-square&logo=amazon-aws&logoColor=white)

### Oracle / SQL
![](https://img.shields.io/badge/SQL-SQL_Intermediate_Certificate-4479A1?style=flat-square&logo=mysql&logoColor=white)

### Google Cloud Platform
![](https://img.shields.io/badge/Google_Cloud-Introduction_to_Generative_AI_Studio-4285F4?style=flat-square&logo=google-cloud&logoColor=white)

### Professional Development
![](https://img.shields.io/badge/Career-AI_and_Career_Empowerment-7B2CBF?style=flat-square&logo=mindshare&logoColor=white)

---

## 08. Coding Profiles

<div align="center">

<a href="https://leetcode.com/">
  <img src="https://img.shields.io/badge/LeetCode-FFA116?style=for-the-badge&logo=leetcode&logoColor=black" alt="LeetCode" />
</a>
<a href="https://geeksforgeeks.org/">
  <img src="https://img.shields.io/badge/GeeksforGeeks-298D46?style=for-the-badge&logo=geeksforgeeks&logoColor=white" alt="GeeksforGeeks" />
</a>
<a href="https://hackerrank.com/">
  <img src="https://img.shields.io/badge/HackerRank-00EA64?style=for-the-badge&logo=hackerrank&logoColor=black" alt="HackerRank" />
</a>
<a href="https://codechef.com/">
  <img src="https://img.shields.io/badge/CodeChef-5B4638?style=for-the-badge&logo=codechef&logoColor=white" alt="CodeChef" />
</a>

</div>

---

## 09. GitHub Analytics

<div align="center">

  <img src="https://github-readme-stats.vercel.app/api?username=itpRakib&theme=dracula&show_icons=true&hide_border=true&title_color=9D4EDD&icon_color=7B2CBF&text_color=F8F8F2&bg_color=0D1117" alt="GitHub Stats" width="49%" />
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=itpRakib&theme=dracula&hide_border=true&background=0D1117&ring=7B2CBF&fire=9D4EDD&currStreakLabel=9D4EDD" alt="GitHub Streak" width="49%" />

  <br/>

  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=itpRakib&theme=dracula&layout=compact&hide_border=true&title_color=9D4EDD&text_color=F8F8F2&bg_color=0D1117" alt="Top Languages" width="49%" />

</div>

---

## 10. GitHub Trophies

<div align="center">

  <img src="https://github-profile-trophy.vercel.app/?username=itpRakib&theme=dracula&column=6&margin-w=15&margin-h=15&no-bg=true" alt="GitHub Trophies" />

</div>

---

## 11. Contribution Activity

<div align="center">

  <img src="https://github-readme-activity-graph.vercel.app/graph?username=itpRakib&theme=react-dark&bg_color=0D1117&hide_border=true&color=9D4EDD&line=7B2CBF&point=FFFFFF" width="100%" alt="Contribution Graph" />

</div>

---

---



## 12. Contribution Snake

<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/itpRakib/itpRakib/output/github-contribution-grid-snake-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/itpRakib/itpRakib/output/github-contribution-grid-snake.svg">
    <img alt="github contribution grid snake animation" src="https://raw.githubusercontent.com/itpRakib/itpRakib/output/github-contribution-grid-snake.svg" width="100%">
  </picture>
</div>

---

## 13. Current Focus

```yaml
current_status:
  learning:
    - Advanced Data Structures & Algorithm Design in C++
    - System Design & Distributed Systems Fundamentals
  building:
    - High-performance full-stack applications with React & Node.js
    - Scalable cloud infrastructure setups on AWS
  exploring:
    - Cloud-native database optimizations and microservices architecture
    - Generative AI integrations for automated engineering workflows
  open_to:
    - Software Engineering Internships
    - Full-Stack / Backend Engineering Roles
    - Open Source Collaboration

---
