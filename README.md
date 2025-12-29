# Python_assignment

def compute_tax(status, income):
    # Tax brackets for 2009
    brackets = {
        0: [  # Single
            (8350, 0.10),
            (33950, 0.15),
            (82250, 0.25),
            (171550, 0.28),
            (372950, 0.33),
            (float('inf'), 0.35)
        ],
        1: [  # Married filing jointly / Qualifying widow(er)
            (16700, 0.10),
            (67900, 0.15),
            (137050, 0.25),
            (208850, 0.28),
            (372950, 0.33),
            (float('inf'), 0.35)
        ],
        2: [  # Married filing separately
            (8350, 0.10),
            (33950, 0.15),
            (68525, 0.25),
            (104425, 0.28),
            (186475, 0.33),
            (float('inf'), 0.35)
        ],
        3: [  # Head of household
            (11950, 0.10),
            (45500, 0.15),
            (117450, 0.25),
            (190200, 0.28),
            (372950, 0.33),
            (float('inf'), 0.35)
        ]
    }
    tax = 0
    previous_limit = 0
    for limit, rate in brackets[status]:
        if income > limit:
            tax += (limit - previous_limit) * rate
            previous_limit = limit
        else:
            tax += (income - previous_limit) * rate
            break
    return tax

# ---- Main Program ----
print("Name: OKE Adedamola Olorunloba")
print("Course: CSC 201 ⇒ Computer Proramming 1")
print("Date: 25/11/2025")
print("--")
print("Filing Status")
print("0 - Single")
print("1 - Married filing jointly / Qualifying widow(er)")
print("2 - Married filing separately")
print("3 - Head of household")
print("--")
print("Enter filing status (0-3):")
status = int(input())
print("Enter taxable income:")
income = float(input())
tax = compute_tax(status, income)
print(f"Total tax is: ${tax:.2f}")
<img width="796" height="1657" alt="image" src="https://github.com/user-attachments/assets/975cd991-bb92-4422-86e3-f3f1e0a53f66" />

