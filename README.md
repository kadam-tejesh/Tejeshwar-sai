resume_data = {
    "name": "Kadam Tejeshwar Sai",
    "contact": {
        "phone": "+91 8919606909",
        "email": "kadamtejesh07@gmail.com",
        "github": "https://github.com/kadam-tejesh"  # update if needed
    },
    "objective": """An enthusiastic engineering aspirant who would like to secure a role in the field of software, where I can apply my technical skills and analytical mindset to develop innovative solutions.""",
    "education": [
        {
            "degree": "B. Tech in Computer Science and Engineering (AI & ML)",
            "institution": "Sri Venkateswara College of Engineering, Tirupati",
            "year": "2022–2026",
            "cgpa": "CGPA: 9.45"
        },
        {
            "degree": "Intermediate (MPC)",
            "institution": "Viswasai Junior College, Tirupati",
            "year": "2020–2022",
            "percentage": "94.9%"
        }
    ],
    "experience": [
        {
            "title": "Data Analyst Intern",
            "company": "Elevate Labs",
            "duration": "Apr 2025 – May 2025",
            "location": "Online",
            "details": [
                "Completed data analysis tasks and developed insights using Python and relevant tools.",
                "Worked effectively in an online environment with a focus on collaboration and communication."
            ]
        },
        {
            "title": "AI-Data Analyst Intern",
            "company": "Rooman Technologies",
            "duration": "May 2025 – Jul 2025",
            "location": "Bangalore",
            "details": [
                "Conducted data analysis, focusing on AI applications within data sets.",
                "Applied machine learning techniques to extract predictions and insights."
            ]
        }
    ],
    "skills": {
        "Programming Languages": ["Python", "Java"],
        "Libraries & Tools": ["NumPy", "Pandas", "Matplotlib", "Scikit-learn", "Seaborn", "Power BI"],
        "Other": ["Data Structures using Java", "MySQL"]
    },
    "projects": [
        {
            "name": "Disease Prediction using Logistic Regression",
            "description": "Developed a binary classification model to predict diabetes using Python and Scikit-learn.",
            "features": ["Model development", "Visualization", "Confusion Matrix for evaluation"]
        },
        {
            "name": "Titanic Survival Prediction",
            "description": "Used Titanic dataset to predict survival chances using machine learning.",
            "features": ["Data cleaning", "Feature selection", "Scikit-learn and Pandas"],
            "link": "https://github.com/kadam-tejesh/Machine-learning-models"
        }
    ],
    "certificates": [
        "Machine Learning – Stanford University & DeepLearning.AI (Coursera)",
        "Data Science – IBM (Infosys Springboard-Coursera)"
    ],
    "soft_skills": ["Leadership", "Decision Making", "Communication", "Time Management"]
}

def generate_readme(data):
    readme = f"# 👋 Hi, I'm {data['name']}\n\n"
    readme += f"📧 **Email:** {data['contact']['email']}  \n"
    readme += f"📞 **Phone:** {data['contact']['phone']}  \n"
    readme += f"🔗 **GitHub:** [{data['contact']['github']}]({data['contact']['github']})\n\n"
    
    readme += f"## 🎯 Career Objective\n{data['objective']}\n\n"
    
    readme += "## 🎓 Education\n"
    for edu in data["education"]:
        readme += f"**{edu['degree']}**, {edu['institution']} ({edu['year']})  \n"
        readme += f"{edu.get('cgpa') or edu.get('percentage')}\n\n"

    readme += "## 💼 Experience\n"
    for exp in data["experience"]:
        readme += f"**{exp['title']}**, *{exp['company']}* ({exp['duration']} - {exp['location']})  \n"
        for detail in exp["details"]:
            readme += f"- {detail}\n"
        readme += "\n"
    
    readme += "## 🛠 Technical Skills\n"
    for category, items in data["skills"].items():
        readme += f"- **{category}:** " + ", ".join(items) + "\n"
    readme += "\n"
    
    readme += "## 📂 Projects\n"
    for proj in data["projects"]:
        readme += f"### {proj['name']}\n"
        readme += f"{proj['description']}\n"
        readme += "- " + "\n- ".join(proj["features"]) + "\n"
        if "link" in proj:
            readme += f"[🔗 Project Link]({proj['link']})\n"
        readme += "\n"

    readme += "## 🧾 Certifications\n"
    for cert in data["certificates"]:
        readme += f"- {cert}\n"
    readme += "\n"

    readme += "## 🤝 Soft Skills\n"
    readme += ", ".join(data["soft_skills"]) + "\n"

    return readme

# Save to README.md
with open("README.md", "w", encoding="utf-8") as file:
    file.write(generate_readme(resume_data))

print("README.md generated successfully!")
