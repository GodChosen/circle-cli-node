#Test jobs locally using CircleCI  CLI
To successfully test jobs locally, I ensured I had the following rerequisites sorted out:
- Install Docker locally
- A CircleCI account
- A Snyk account
- Create a new Snyk API token
- Add my local project to CircleCI
- Create a CircleCI personal API token 
- Install CircleCI CLI tool locally
- Run the CLI setup using the API token


## Install CircleCI
- I used chocolatey to install CircleCI on my Windows PC
`choco install circleci-cli -y`

- To configure circleci, I used the following command
`circleci setup --no-prompt --host https://circleci.com --token circleci_token`

- To validate circleci config, I used the following command
`circleci config validate`


### Install snyk to check for vulnerability
- I created a Snyk account.
- To install Snyk CLI, I ran the following codes.
```
npm i snyk -g
snyk auth [<SNYK_TOKEN>]
```
- Note that you could store Snyk token as an environment variable for later use

## Run Test locally
To run the test locally, I created the two scripts below:
- test-jobs-locally.sh
The script when run test the job locally.
The code to run the script is: 
`./.circleci/test-jobs-locally.sh <job_name>`

- vulnerability-scan-locally.sh
The script scans for security vulnerability.
The code to run the script is: 
`./.circleci/vulnerability-scan-locally.sh <vulnerability_scan_job_name>`

