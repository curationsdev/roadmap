# Sample Roadmap Issues

This file contains ready-to-create sample issues for maintainers to paste into GitHub Issues. These examples demonstrate how to structure roadmap items and provide a starting point for the CurationsLA roadmap.

---

## Issue 1: Ability for Curators (Subscribers) to upvote

**Title**: `[roadmap] [Q1 2026] Ability for Curators (Subscribers) to upvote`

**Labels**: `roadmap`, `type/feature`, `priority/high`

**Milestone**: Q1 2026

**Body**:
```markdown
## Brief summary
Allow Curators (subscribers) to upvote roadmap items and listings.

## Why this matters
Enables community prioritization and surfaces high-impact requests. This feature empowers the curator community to have a direct say in what gets built, ensuring that development efforts align with actual user needs and priorities.

## Suggested priority
- [ ] Low
- [ ] Medium
- [x] High

## Estimated effort
Medium

## Suggested quarter
Q1 2026

## Any design or references
- Google Form for public votes
- Tie votes to issue counts
- Display vote counts on user profiles
- Consider implementing upvote notifications

## Additional notes
This is a foundational feature for community engagement. Should integrate with the Google Form voting system for users without GitHub accounts.
```

---

## Issue 2: Curators can submit their business to feature on neighborhood pages

**Title**: `[roadmap] [Q1 2026] Curators can submit their business to feature on neighborhood pages`

**Labels**: `roadmap`, `type/feature`, `priority/medium`

**Milestone**: Q1 2026

**Body**:
```markdown
## Brief summary
Add a submission flow so Curators can propose businesses for neighborhood feature pages.

## Why this matters
Empowers local curators to add and promote local businesses, increasing engagement and content quality. This creates a virtuous cycle where curators become more invested in the platform by contributing their local knowledge and expertise.

## Suggested priority
- [ ] Low
- [x] Medium
- [ ] High

## Estimated effort
Small/Medium

## Suggested quarter
Q1 2026

## Any design or references
- Simple form submission interface
- Review/approval workflow for maintainers
- Notification system when submissions are approved/rejected
- Integration with existing neighborhood pages

## Additional notes
Status: In-Progress (drafting for Q1 2026). Consider implementing moderation queue to maintain quality.
```

---

## Issue 3: Neighborhood aggregated metrics and trends

**Title**: `[roadmap] [Q2 2026] Neighborhood aggregated metrics and trends`

**Labels**: `roadmap`, `type/feature`, `priority/medium`

**Milestone**: Q2 2026

**Body**:
```markdown
## Brief summary
Display aggregated metrics and trend data for each neighborhood, showing activity levels, popular categories, and growth over time.

## Why this matters
Provides valuable insights to curators and business owners about neighborhood engagement and popularity. Helps identify emerging trends and opportunities for business development in specific areas.

## Suggested priority
- [ ] Low
- [x] Medium
- [ ] High

## Estimated effort
Medium

## Suggested quarter
Q2 2026

## Any design or references
- Dashboard with charts and graphs
- Time-series data visualization
- Comparison tools between neighborhoods
- Export functionality for reports

## Additional notes
Requires backend analytics infrastructure. Consider privacy implications and data aggregation strategies.
```

---

## Issue 4: Public profiles for Curators

**Title**: `[roadmap] [Q3 2026] Public profiles for Curators`

**Labels**: `roadmap`, `type/feature`, `priority/medium`

**Milestone**: Q3 2026

**Body**:
```markdown
## Brief summary
Create public profile pages for Curators showcasing their contributions, specialties, and favorite neighborhoods.

## Why this matters
Builds credibility and recognition for active curators, incentivizing quality contributions. Public profiles create a sense of community and allow users to follow their favorite curators.

## Suggested priority
- [ ] Low
- [x] Medium
- [ ] High

## Estimated effort
Large

## Suggested quarter
Q3 2026

## Any design or references
- Profile customization options
- Activity feed showing recent contributions
- Badges/achievements for milestones
- Social sharing capabilities
- Links to curator's submitted businesses

## Additional notes
Consider privacy settings and allow curators to control what information is publicly visible.
```

---

## Issue 5: Listings export / partner integrations

**Title**: `[roadmap] [Q4 2026] Listings export / partner integrations`

**Labels**: `roadmap`, `type/feature`, `priority/medium`

**Milestone**: Q4 2026

**Body**:
```markdown
## Brief summary
Enable export of listings data and build integration capabilities with partner platforms and services.

## Why this matters
Expands the reach and utility of CurationsLA data, creating value for both the platform and partner organizations. Allows businesses to leverage their listings across multiple platforms.

## Suggested priority
- [ ] Low
- [x] Medium
- [ ] High

## Estimated effort
Large

## Suggested quarter
Q4 2026

## Any design or references
- API endpoints for partner access
- Export formats: CSV, JSON, XML
- OAuth integration for secure access
- Rate limiting and usage analytics
- Documentation for integration partners

## Additional notes
Need to establish partnership agreements and data usage policies before implementation. Consider monetization opportunities.
```

---

## Creating these issues

To create any of these issues in the GitHub repository:

1. Go to https://github.com/curationsdev/roadmap/issues/new
2. Copy the title from above
3. Add the specified labels
4. Set the milestone
5. Paste the body content
6. Submit the issue

## Customizing issues

When creating your own roadmap issues:

- Use the `[roadmap]` prefix in titles for easy filtering
- Include the target quarter in brackets: `[Q1 2026]`
- Apply consistent labels: `roadmap`, `type/feature`, `priority/high|medium|low`
- Fill out all sections of the template
- Link related issues where applicable
- Update ROADMAP.md and docs/index.md to reflect the new issue

---

**Maintainers**: Remember to keep ROADMAP.md and docs/index.md in sync with GitHub Issues.
