# Contributing to HR Analytics Dashboard

Thanks for your interest in improving this project. All kinds of contributions are welcome: bug reports, new visualisations, better insights and documentation fixes.

## How to Contribute

1. **Fork** the repository.
2. **Clone** your fork:
   ```bash
   git clone https://github.com/<your-username>/<repo-name>.git
   ```
3. Create a new branch:
   ```bash
   git checkout -b feature/your-feature-name
   ```
4. Make your changes (see guidelines below).
5. Commit with a clear message:
   ```bash
   git commit -m "Add: attrition by tenure chart"
   ```
6. Push and open a **Pull Request**:
   ```bash
   git push origin feature/your-feature-name
   ```

## Guidelines

- Keep the existing dashboard style (colours, fonts, layout) consistent.
- Give every new sheet a clear name, e.g. `Attrition by Tenure`.
- Do not commit large Tableau extracts (`.hyper`, `.tde`); use the shared dataset in `data/` instead.
- Do not upload confidential or personally identifiable employee data.
- Update `README.md` if you add or change a sheet or KPI.
- Add a screenshot of your change to the pull request.

## Reporting Issues

Open an issue and include:

- A short description of the problem or suggestion
- Steps to reproduce (if it is a bug)
- A screenshot, if relevant
- Your Tableau version

## Ideas for Contributions

- Attrition by tenure, salary band or overtime
- Monthly income vs. attrition analysis
- Mobile / phone layout for the dashboard
- Additional filters (department, job role, marital status)

## Code of Conduct

Be respectful and constructive in all discussions and reviews.
