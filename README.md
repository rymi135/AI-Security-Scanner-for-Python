<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# AI Security Scanner for Python

**Project Link:** [View Project](http://learn.nextwork.org/projects/ai-security-audit)

**Author:** Ryan Robson  
**Email:** ryan.robson2003@gmail.com

---

![Image](http://learn.nextwork.org/relaxed_vermilion_timid_bat/uploads/ai-security-audit_sec4e5f6)

---

## Introducing Today's Project!

In this project, I'm going to build a CLI tool that allows me to understand code the could be vulnerable to attacks resulting in future faults. 
This will give me help me learn what does vulnerable code look like, how to use the Gemini API and how to fix vulnerable code. I'm interested in this because companies like Google and Synk utilise AI to spot vulnerabilites in code early so that they don't become a larger problem in production. 

### Key tools and concepts

Tools I used were Python and Gemini. Key concepts I learnt include are environment variables, good coding practices (to avoid vulnerable code) and API's. The most important skill was building and understanding arounf why you don't want to write vulnerable code.

### Challenges and wins

This project took me approximately 1.5 hours. The most challenging part was understanding how to take arguments from the terminal. It was most rewarding to see the working scanner reports working on real code.

### Why I did this project

I did this project today because I wanted learn how to make my code less vulnerable efficiently (using Gemini API). This project met my goals by improving my understanding around what vulnerable code looks and how to prevent it from getting into production. Next, I plan to improve my CLI tool by increasing functionality around how many files I can scan through at once.

---

## Connecting to Gemini API

In this step, I'm setting up the Gemini API connection. This involves creating an .env file and adding the Gemini API key to it.  
I need to do this so I can test (and verify) my connection to Gemini. Run python -m venv venv to download venv and venv\Scripts\activate to start the environment

![Image](http://learn.nextwork.org/relaxed_vermilion_timid_bat/uploads/ai-security-audit_sec2c3d4)

I verified the connection by running 'python scanner.py'. Gemini responded with 'Hello security scanner!' which confirms that the API was correctly setup and linked to Google's servers.

![Image](http://learn.nextwork.org/relaxed_vermilion_timid_bat/uploads/ai-security-audit_sec4e5f6)

My scanner.py file works by sending a prompt to gemini with the specified code. 
When I ran it, Gemini identified multiple issues, namly the plain text storage of the password, hardcoded values, no hashing, etc. 
This shows that the Gemini API can detect vulnerabilites in my code. 

---

## Building the Vulnerability Scanner

In this step, I'm building a vulnerability scanner that will detect SQL injection, hardcoded secrets and weak passwords. This will allow me to write production ready code.

![Image](http://learn.nextwork.org/relaxed_vermilion_timid_bat/uploads/ai-security-audit_sec7h8i9)

The vulnerabilities Gemini detected were SQL injection, hardcoded passwords and poor encryption. The security prompt I crafted asked for a vulnerability type, why it's vulnerable, the impact and a code fix. This structured output helps me resolve the code that is vulnerable.

---

## Adding Severity Ratings

In this step, I'm adding severity ratings that rank the severity of a specific vulnerability (CRITICAL, HIGH, MEDIUM, and LOW).
I'm also installing colorama to display the different rankings as different colours. 

![Image](http://learn.nextwork.org/relaxed_vermilion_timid_bat/uploads/ai-security-audit_sec0k1l2)

I updated the security prompt to include a 'SEVERITY' level. The add_colors_to_output function works by replacing existing text with coloured text using the 'colorama' python library. When I see CRITICAL in red, it tells me that it requires an urgent fix.

---

## Scanning Real Python Files

I'm adding a function to scan external files and creating a vulnerable file to test with. This lets the scanner work on external files, not just stuff we pass in. Professional tools do this because they allow developers to pass in large files(not snippets) and have them analysed.

![Image](http://learn.nextwork.org/relaxed_vermilion_timid_bat/uploads/ai-security-audit_sec3n4o5)

I scanned vulnerable.py by running python scanner.py vulnerable.py . The vulnerabilities detected were hardcoded credentials, SQL injection and weak hashing. The scan_file function works by passing in the 1st index from the user's terminal input (sys_argv[1]) as the input to the scan_file function.

---

## Wrap-up

---

---
