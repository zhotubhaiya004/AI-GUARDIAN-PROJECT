# AI-GUARDIAN-PROJECT
AI Guardian is a responsible AI system created to protect users from online scams, fraudulent messages, and harmful digital interactions. As AI-generated content continues to grow, threats such as phishing attacks, deepfake scams, and misinformation are becoming more common and harder to identify.
# AI Guardian - Scam Message Detector
# Works without external libraries

# Scam keywords database
scam_keywords = [
    "win",
    "free",
    "click",
    "offer",
    "urgent",
    "bank",
    "verify",
    "prize",
    "money"
]

print("AI Guardian System Ready")

# Function to calculate risk score
def calculate_risk(message):

    message = message.lower()

    score = 0

    for word in scam_keywords:
        if word in message:
            score += 1

    risk_percent = score * 10

    if risk_percent >= 50:
        label = "SCAM"
    else:
        label = "SAFE"

    return label, risk_percent


# Main program loop
while True:

    user_message = input("\nEnter message (type exit to stop): ")

    if user_message.lower() == "exit":
        print("AI Guardian stopped.")
        break

    result, risk = calculate_risk(user_message)

    print("\nResult:", result)
    print("Risk Score:", risk, "%")
