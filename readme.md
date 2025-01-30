# Tutor Open edX Automated Setup with Ansible

## Overview
This project automates the setup of Open edX using Tutor, clones the required repositories (Tutor_setup and frontend-app-authn), and ensures a fully automated deployment using Ansible.

## Key Decisions
- **Ansible for Automation**: Using Ansible ensures consistent and repeatable deployments.
- **Git Repository Setup**: Make sure that you put this tutor-setup and frontend-app-authn in the same folder
- **Tutor as the Deployment Tool**: Tutor simplifies Open edX deployment and maintenance.
- **Automated Execution**: Running Ansible automates installation and configuration without manual intervention.
- **Self-Hosted vs. Cloud Deployment**: This setup is intended for on-premises deployment using Docker Compose, but it can be extended for cloud-based Kubernetes deployments.

## Trade offs
- **Performance vs. Ease of Deployment**: Automating everything ensures easy deployment but can be slower for first-time setup.
- **Ansible vs. Manual Configuration**: Automating the setup reduces errors but requires familiarity with Ansible.
- **Parallelism in BuildKit**: BuildKit is configured with `max-parallelism = 1` to manage CPU usage efficiently, but it is slowing down build process.

## Potential Improvements for Production
- **Scalability**: Deploy on Kubernetes instead of Docker Compose for better scaling.
- **CI/CD Integration**: Automate testing and deployment pipelines with GitHub Actions or GitLab CI/CD.
**Monitoring and Logging**: Integrate tools like Prometheus, Grafana etc.
**Load Balancing and Caching**: Implement caching mechanisms

## How to Set Up
### Prerequisites
- Docker and Docker Compose installed
- Ansible installed

### Steps
1. Clone this repository:
   ```bash
   git clone https://github.com/YOUR_GITHUB_USERNAME/tutor-setup.git
   cd tutor-setup
   ```

3. Fork and clone the frontend-app-authn repository:
   ```bash
   git clone https://github.com/YOUR_GITHUB_USERNAME/frontend-app-authn.git mfe/frontend-app-authn
   ```

4. Run the Ansible playbook to install and configure everything:
   ```bash
   ansible-playbook main.yml
   ```

5. Access the Open edX instance:
   ```bash
   http://local.openedx.io/
   ```

## Repository Structure
```
tutor-setup/
│── roles/
│   ├── ansible-role-tutor/
        ── tasks.yml
        ── ansible-role-tutor.yml
    ├── main.yml
│
│── frontend-app-authn/             
│── README.md 
```

## Author
- YAGNESH ARVINDBHAI PANSURIYA  
- yagneshpansuriya78@gmail.com