📘 Roboshop – Ansible Roles :-

Overview

This project automates the end-to-end deployment of all Roboshop microservices using Ansible Roles.
Each microservice (catalogue, user, cart, payment, shipping, mongodb, mysql, redis, rabbitmq, nginx) is fully automated using reusable role components.

📁 Project Structure Explained (Simple One-Line Explanation for Each)

🧩 What Each Component Does

tasks/
Main logic for installing packages, creating users, copying files, starting services, loading schemas, and configuring the application.

handlers/
Actions that trigger when something changes, such as restarting or reloading services after template or config updates.

templates/
Dynamic Jinja2 (.j2) templates used for systemd service files, application configs, and reverse proxy configurations.

files/
Static files that must be copied to the server without modification, such as schema files or prebuilt configuration files.

vars/
Variable values used by tasks and templates, typically service-specific settings like package names, ports, or paths.

🚀 How It Works

Choose the microservice to deploy using -e component=<service-name>.

main.yml automatically loads the correct role.

Each role installs packages, configures systemd, downloads application code, starts services, and loads DB schemas if needed.

▶️ Run the Playbook
ansible-playbook -i inventory.ini main.yml -e component=catalogue

✔️ Features

1.Fully automated microservice deployment

2.Consistent Linux/systemd setup

3.Template-based config generation

4.DB schema loading for MongoDB/MySQL

5.Reusable role structure

6.Production-style folder layout
