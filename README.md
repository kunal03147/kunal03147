from reportlab.lib import colors
from reportlab.lib.pagesizes import letter
from reportlab.platypus import SimpleDocTemplate, Paragraph, Spacer
from reportlab.lib.styles import getSampleStyleSheet

def create_pdf(file_name, content):
    doc = SimpleDocTemplate(file_name, pagesize=letter)
    styles = getSampleStyleSheet()
    flowables = []

    for text in content:
        para = Paragraph(text, styles["Normal"])
        flowables.append(para)
        flowables.append(Spacer(1, 12))

    doc.build(flowables)

# Example content for the document
content = [
    "Chapter 1: Introduction to Physics",
    "- Overview of Physics",
    "- Historical Development",
    "- Fundamental Concepts and Principles",
    "",
    "Chapter 2: Mechanics",
    "- Kinematics",
    "- Dynamics",
    "- Energy and Momentum",
    "- Rotational Motion",
    "- Gravitation",
    # Add more chapters and content as needed
]

# Create the PDF document
create_pdf("physics_compendium.pdf", content)
