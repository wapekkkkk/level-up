# Level Up: Project Brief

Author: Wafiq | Version 0.1 (draft) | 28 October 2026

## 1. Problem statement

Many gym beginners and casual lifters do not track their workouts consistently. Paper notes and generic note apps are tedious, and without visible progress people lose motivation and stop training. Existing fitness apps are often cluttered, locked behind subscriptions, or built around features (social feeds, nutrition, wearables) that a user who just wants to log lifts does not need.

**Level Up** is a gamified workout tracker for web and mobile. It makes logging fast and rewarding by turning consistent training into XP, levels, and achievements.

## 2. Objectives

1. Let a user record a complete workout (exercises, sets, reps, weight) in under 2 minutes.
2. Show workout history and progress trends so users can see improvement over time.
3. Reward consistency with XP, levels, and a small set of achievements, with no duplicate awards.
4. Keep each user's data private: user A can never read or change user B's records.
5. Deliver the project as a learning exercise covering the full SDLC, with documentation, design, tests, and deployment evidence for every phase.

## 3. Target users

- **Primary: gym user.** A beginner or casual lifter who wants simple logging and visible progress.
- **Secondary: administrator.** The developer, who manages the shared exercise catalogue and achievement definitions.

## 4. Scope

**In scope (version 1.0)**

- Register, login, logout, password recovery
- User profile and fitness goals
- Exercise library
- Workout sessions and sets (reps, weight)
- Workout history and basic charts
- XP, levels, and a few achievements
- Secure access to personal records (RLS)

**Out of scope (deferred)**

- Social feed and leaderboards
- AI workout generation
- Wearable integrations
- Nutrition and calorie tracking
- Payments and subscriptions
- Push notifications and advanced offline sync

## 5. Proposed solution and tools

Ionic + Angular + TypeScript frontend, Supabase (Auth, PostgreSQL, RLS, Edge Functions) backend, Capacitor for the Android build, GitHub for source control and CI, Figma for UI/UX. The web MVP is built and tested first, then packaged for Android.

## 6. Constraints and assumptions

- **Time:** 8-12 hours per week; 12 weeks planned, 14-16 weeks realistic.
- **Budget:** RM0 per month, using free tiers only (to be verified against providers' current terms).
- **Team:** solo developer who is learning Ionic, Angular, SQL, and testing along the way.
- **Platforms:** web first, Android second; iOS release is not planned because it needs macOS and paid Apple tooling.
- **Assumption:** Supabase free-tier limits (database size, storage, inactivity pausing) are sufficient for a learning MVP with a small number of test users.

## 7. Feasibility summary

- **Technical:** feasible. All chosen tools are mainstream, well documented, and free to start with.
- **Schedule:** feasible if scope stays fixed; the main risk is the learning curve, mitigated by the buffer weeks.
- **Cost:** feasible within RM0 if usage stays inside free quotas.
- **Skills gap:** Angular, SQL/RLS, and testing are new and will be learned during the build.

## 8. Initial risks

| Risk | Impact | Mitigation |
| --- | --- | --- |
| Scope creep (adding social, AI, nutrition) | Schedule slips | Keep the out-of-scope list frozen until v1.0 ships |
| Learning curve slows delivery | Delays | Plan for 14-16 weeks; build small vertical slices |
| Weak RLS policies leak user data | Security failure | Write and test policies alongside each table |
| XP awarded twice on retry | Data integrity | Server-side, idempotent XP logic with a uniqueness constraint |
| Supabase free project pauses or hits limits | Downtime | Keep schema and seed data in Git migrations; review quotas |

## 9. Success criteria (Definition of Done)

- SRS, user stories, UI designs, ERD, and architecture diagram completed
- Authentication, workout logging, history, statistics, and gamification working
- RLS and cross-user access tests pass; XP cannot be duplicated by retries
- Unit, integration, end-to-end, and usability tests documented
- Web app deployed; Android build tested on an emulator or device
- Setup guide, user guide, deployment and rollback notes, and release notes ready
- Retrospective records lessons learned, defects, technical debt, and next steps

## 10. Next phase

Requirements (Week 2): user stories with acceptance criteria, functional and non-functional requirements with IDs (FR-01, NFR-01), use cases for the critical flows, XP and level rules, and a full risk register.
