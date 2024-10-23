# Setup!
Follow The Steps in order
- First : Setup the appsettings.json to fit the database login
  - After the default, instead of "", put
    ```json
    "Server=[ServerNamer];Database=[TheDatabaseNameYouWant];Trusted_Connection=True;MultipleActiveResultSets=true;TrustServerCertificate=true"
    ```
- Second : Do the migration by going in your package manager console and writing : 
  - add-migration "init"
- Third : Update the database to create the table with the following command in the package manager console
  - update-database
- Fourth : You can also change the Jwt token as you wish in the application.json


# How does the authentification Works?

Basically, when the user creates the account, everything is sent to the database. After that, if the user tries to connect, it will automatically assign a Jwt token to the user. This token can then be used by the user in the following request he makes so that he is authorized to access the endpoint. The token expires after a while so there will be a need to sign in again at some point.