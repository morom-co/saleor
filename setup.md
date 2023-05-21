## Backend
1. Install docker
2. Install docker-compose
3. `cd .devcontainer && docker-compose up -d saleor`
4. To create dev data and admin user
    -  `docker exec -it devcontainer_saleor_1 bash` 
    - `python3 manage.py populatedb`
    - `python3 manage.py createsuperuser`

- For logs `docker-compose logs -f saleor`

## Frontend
- Install node v18
- `cd saleor-dashboard`
- `npm install`
- Copy `.env.example` to `.env` and update the values as follows:
    ```
    API_URI=http://localhost:8000/graphql/
    APP_MOUNT_URI=/dashboard/
    APPS_MARKETPLACE_API_URI=https://apps.saleor.io/api/v2/saleor-apps
    STATIC_URL=http://localhost:9000/
    ```
- `npm run build`
- `npx vite preview --port 9000`


## Branching
- `main` is copy of original repo
- `stable` is the release branch. Anything merged to this branch will be deployed
  - Raise your PRs against `stable` branch.
