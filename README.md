# Designing a Bank Marketing Database
This is a simple Data Importing and Cleaning project along with Data Modeling that I did based on Python and PostgreSQL.

I took a csv file called `"bank_marketing.csv"`, which needed to clean, reformat, and split, in order to save separate files based on the tables you will create. It was done using pandas.


After that, I wrote code to populate the Database. 
## client

| column | data type | description | original column in dataset |
|--------|-----------|-------------|----------------------------|
| `id` | `serial` | Client ID - primary key | `client_id` |
| `age` | `integer` | Client's age in years | `age` |
| `job` | `text` | Client's type of job | `job` |
| `marital` | `text` | Client's marital status | `marital` | 
| `education` | `text` | Client's level of education | `education` |
| `credit_default` | `boolean` | Whether the client's credit is in default | `credit_default` |
| `housing` | `boolean` | Whether the client has an existing housing loan (mortgage) | `housing` | 
| `loan` | `boolean` | Whether the client has an existing personal loan | `loan` |

<br>

## campaign

| column | data type | description | original column in dataset |
|--------|-----------|-------------|----------------------------|
| `campaign_id` | `serial` | Campaign ID - primary key | N/A - new column |
| `client_id` | `serial` | Client ID - references `id` in the `client` table | `client_id` |
| `number_contacts` | `integer` | Number of contact attempts to the client in the current campaign | `campaign` |
| `contact_duration` | `integer` | Last contact duration in seconds | `duration` |
| `pdays` | `integer` | Number of days since contact in previous campaign (`999` = not previously contacted) | `pdays` |
| `previous_campaign_contacts` | `integer` | Number of contact attempts to the client in the previous campaign | `previous` |
| `previous_outcome` | `boolean` | Outcome of the previous campaign | `poutcome` |
| `campaign_outcome` | `boolean` | Outcome of the current campaign | `y` |
| `last_contact_date` | `date` | Last date the client was contacted | A combination of `day`, `month`, and the newly created `year` |

<br>

## economics

| column | data type | description | original column in dataset |
|--------|-----------|-------------|----------------------------|
| `client_id` | `serial` | Client ID - references `id` in the `client` table | `client_id` |
| `emp_var_rate` | `float` | Employment variation rate (quarterly indicator) | `emp_var_rate` |
| `cons_price_idx` | `float` | Consumer price index (monthly indicator) | `cons_price_idx` |
| `euribor_three_months` | `float` | Euro Interbank Offered Rate (euribor) three month rate (daily indicator) | `euribor3m` |
| `number_employed` | `float` | Number of employees (quarterly indicator)| `nr_employed` |
