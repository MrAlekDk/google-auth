Open the Google Cloud Console website.
Click the dropdown menu in the top navigation bar and choose "New Project" to create a new project.
Give your project a name and select your billing account if prompted.
Once your project is created, select it from the project dropdown menu in the top navigation bar.
In the left sidebar, select "APIs & Services" and then choose "Dashboard".
Click the "+ ENABLE APIS AND SERVICES" button.
Use the search bar to find "Google+ API" and select it from the results.
Click the "Enable" button to activate the API for your project.
In the left sidebar, select "Credentials".
Click the "+ CREATE CREDENTIALS" button and choose "OAuth client ID".
Select "Web application" as the application type.
Give your client ID a name.
Add "http://localhost:3000/auth/google/callback" as an Authorized redirect URI (replace "localhost:3000" with your application's domain and port if different).
Click the "Create" button.
Your client_id and client_secret will be displayed on the next page. Copy and paste them into your .env file.