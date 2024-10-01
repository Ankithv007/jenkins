# Simple Notes App for TWS Community
This is a simple notes app built with React and Django.

## Requirements
1. Python 3.9
2. Node.js
3. React

## Installation
1. Clone the repository
```
git clone https://github.com/Ankithv007/jenkins.git
```

2. Build the app
```
docker build -t notes-app .
```

3. Run the app
```
docker run -d -p 8000:8000 notes-app:latest
```
## Nginx

Install Nginx reverse proxy to make this application available

`sudo apt-get update`
`sudo apt install nginx`



# git clone example
-In the terminal, navigate to your project folder (if you haven't already):
`cd /path/to/your/project`
- Initialize a new Git repository:
`git init`
- Add Your Project Files
`git add .`
- Commit your changes with a descriptive message:
`git commit -m "Initial commit"`
- Connect Your Local Repository to the GitHub Repository
  `git remote add origin https://github.com/<username>/<repo-name>.git`
- for example
  `git remote add origin https://github.com/Ankithv007/my-project.git`
  - Push Your Changes to GitHub
    `git push -u origin main`

 ```
    cd /path/to/your/project       # Navigate to your project directory
git init                        # Initialize a new Git repository
git add .                       # Stage all files
git commit -m "Initial commit"  # Commit changes
git remote add origin https://github.com/<username>/<repo-name>.git  # Add remote repository
git push -u origin main        # Push changes to GitHub

```
