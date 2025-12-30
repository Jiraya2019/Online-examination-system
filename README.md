# Online Examination System (Console Based)

users = {
    "student1": "1234",
    "student2": "abcd"
}

questions = [
    {
        "question": "What is the capital of India?",
        "options": ["A. Chennai", "B. Delhi", "C. Mumbai", "D. Kolkata"],
        "answer": "B"
    },
    {
        "question": "Which language is used for AI?",
        "options": ["A. Python", "B. HTML", "C. CSS", "D. XML"],
        "answer": "A"
    },
    {
        "question": "Which data structure uses FIFO?",
        "options": ["A. Stack", "B. Tree", "C. Queue", "D. Graph"],
        "answer": "C"
    }
]

def login():
    print("=== Student Login ===")
    username = input("Enter Username: ")
    password = input("Enter Password: ")

    if username in users and users[username] == password:
        print("\nLogin Successful!\n")
        return True
    else:
        print("\nInvalid Login!\n")
        return False

def conduct_exam():
    score = 0
    print("=== Online Examination Started ===\n")

    for i, q in enumerate(questions, 1):
        print(f"Q{i}. {q['question']}")
        for option in q["options"]:
            print(option)
        ans = input("Enter your answer (A/B/C/D): ").upper()

        if ans == q["answer"]:
            score += 1
        print()

    return score

def result(score):
    print("=== Exam Result ===")
    print(f"Total Questions: {len(questions)}")
    print(f"Correct Answers: {score}")
    print(f"Score: {score}/{len(questions)}")

    if score >= 2:
        print("Status: PASS")
    else:
        print("Status: FAIL")

# Main Program
if login():
    score = conduct_exam()
    result(score)
else:
    print("Exiting System...")
