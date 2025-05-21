COMMAND TO RUN DOCKER FILE
docker compose up -d

Best Practices for Pushing WordPress to GitHub
You generally should not push the entire WordPress core to Git. Instead, push only the parts you actually work on — typically the wp-content directory and your custom configurations.

🗂️ Recommended Directory Structure for Git
Here’s a safe and common way to structure your WordPress project in Git:
my-wordpress-project/
├── wp-content/               # Custom themes/plugins/uploads
│   ├── themes/
│   └── plugins/
├── docker-compose.yml        # Your Docker setup
├── .gitignore
└── README.md

You only version-control the wp-content folder, not the full WordPress installation.

Here’s a .gitignore to use:

# Ignore everything except wp-content
*
!.gitignore
!wp-content/
!docker-compose.yml
!README.md

# Inside wp-content, you might want to exclude uploads
wp-content/uploads/

This keeps your Git repo clean and avoids tracking:
	The WordPress core files (which can be downloaded)
	Database files
	Media uploads (which can be heavy and unnecessary for source control)

