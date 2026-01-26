# 🐳 Docker: Handling Build Cache & Environment Sync

Today, I tackled a common issue where Docker containers continue to run outdated code versions despite local changes.

### 🛠️ The Solution
When standard restarts fail to reflect code changes due to aggressive caching:
* **Command:** `docker compose up --build --force-recreate`
* **Why it works:** * `--build` forces Docker to re-compile the images.
    * `--force-recreate` ensures that even if the configuration hasn't changed, the containers are destroyed and started fresh.

### 💡 Insight
Deep-cleaning the Docker environment is often the fastest way to debug "it works on my machine but not in the container" scenarios.
