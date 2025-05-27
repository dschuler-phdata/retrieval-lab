# Retrieval Lab

## Required Setup

### 1. Create a Snowflake Trial Account
Create a new trial account [here](https://signup.snowflake.com), selecting 'Enterprise' as the Snowflake edition 'Azure' as the cloud provider, and 'East US-2' as the region. Note that it may take a few minutes to get teh email from Snowflake to activate the account.

### 2. Create API Integration for GitHub
Once in the Snowsight UI for your trial account, click `+ Create` and choose `SQL Worksheet`. In the worksheet, run the following code to enable an integration with GitHub:
```sql
create or replace api integration RETRIEVAL_LAB_INTEGRATION
    api_provider = git_https_api
    api_allowed_prefixes = ('https://github.com/dschuler-phdata/retrieval-lab')
    enabled = true
    allowed_authentication_secrets = all
;
```

### 3. Link this Repository
- Click `+ Create`, choose `Notebook`, then `From Git Repository`
- on `File location in repository` click, `Create Git Repository`
- Paste this repo URL (https://github.com/dschuler-phdata/retrieval-lab) into the Repository URL field
- Select the newly created API Integration
- Click `+ Database` and name it `RETRIEVAL_LAB`
- Click `Create`
- Select the `retrieval-lab.ipynb` file
- This will send you back to the notebook creatation view where you can just click `Create` to finish the connection process