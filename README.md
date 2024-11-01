# OOB Source Control Template

This repository serves as a template for initializing source control in new projects. It is designed to be downloaded and used for each project where version control will be employed.

## How to Use

1. **Download the repository:**
   - Click the *Code* button above.
   - Select *Download ZIP*.
   - Extract the ZIP file to a directory of your choice.

2. **Initialize Git in your project:**
   - Open a terminal in the directory where you extracted the files.
   - Run the following command to initialize Git, rename the default branch to `main`, add the files to version control, and make the first commit:
     ```bash
     git init && git branch -m main && git add . && git commit -m "init"
     ```

3. **Push to GitHub:**
   - Create a new repository on GitHub.
   - Push your local repository to GitHub using:
     ```bash
     git remote add origin <your-repository-url>
     git push -u origin main
     ```

4. **Set up Remote Repository**
    - In your project directory, authorize the production org and sandbox org by running the appropriate commands.
    - After authorizing each org, run the following command to display org details:
      ```bash
      sfdx force:org:display --verbose
      ```
    - Copy the SFDX Auth URL for each org.
    - Create the following GitHub secrets:
      ```
      Label: SFDX_AUTH_URL_PROD      Secret: <sfdx auth url you copied after authorizing prod>
      Label: SFDX_AUTH_URL_PARTIAL   Secret: <sfdx auth url you copied after authorizing partial>
      ```
    - Ensure the branch structure follows this pattern:
      ```
      main
      partial
      dev-name1
      dev-name2
      ...
      ```

**Note:** Do **not** clone this repository directly, as you do not need the git history. Instead, download it as described above.
