# GitHub Quant Developer Scouting Agent

**Developer**: MD Auj Khan

## Project Summary

This application is an AI-powered GitHub developer discovery tool specifically designed for recruiting quantitative finance professionals. It searches GitHub profiles using advanced filtering criteria and provides intelligent scoring and ranking of candidates based on their technical skills, repository activity, and domain expertise.

### Key Features

- **Advanced Search & Filtering**: Searches for developers with ≥2 repositories in Python or C++, specific quantitative keywords (backtesting, quant, pnl, alpha, risk, strategy), and ≥10 stars OR ≥50 commits
- **Intelligent Scoring System**: Calculates a comprehensive "Quant Score" based on keyword matching, repository analysis, and contribution metrics
- **Professional Profile Cards**: Displays enhanced developer profiles with repository stats, programming languages, and matching criteria
- **CSV Export Functionality**: Generates downloadable CSV reports with developer data for recruitment tracking
- **Real-time Search**: Provides instant feedback with loading states and error handling
- **Responsive Design**: Optimized for all screen sizes with modern UI/UX

### Technical Approach

The application uses React with TypeScript for type safety and maintainable code. It integrates with the GitHub API to search users and analyze their repositories, calculating scores based on multiple criteria including bio keyword matching, repository languages, star counts, and commit activity. The scoring algorithm weights different factors to identify the most qualified quantitative developers.

Error handling is implemented throughout the application with graceful fallbacks and user-friendly error messages. The CSV export feature generates properly formatted files with all relevant developer metrics for easy import into recruitment systems.

## Major Challenge Faced

The primary challenge was implementing accurate commit counting across multiple repositories while respecting GitHub API rate limits. The GitHub API doesn't provide direct access to total commit counts per user, requiring individual API calls to each repository's contributors endpoint. This created performance bottlenecks and potential rate limiting issues.

**Solution**: Implemented intelligent batching and caching strategies, focusing on the top 5 most active repositories per user to balance accuracy with performance. Added comprehensive error handling to gracefully degrade functionality when API limits are reached, ensuring the application remains functional even under constraints.



---

**Integrity Token**: The application generates a unique `integrity_token` on each run to ensure data integrity and track export sessions. This token is included in all CSV exports for audit trail purposes.
