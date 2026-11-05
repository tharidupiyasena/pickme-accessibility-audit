# PickMe Android Accessibility Audit

An independent accessibility case study examining how people using screen readers or with low vision may encounter barriers in the PickMe Android app.

This project brings together a visual audit report, an interactive website, timestamped TalkBack evidence, and structured findings. It documents **five findings across sampled screens**, with a coverage matrix for **12 categories and 72 subtopics**.

> Findings apply to the recorded sample of PickMe **26.100.0-LkPrd**, reviewed on **4 November 2026**. Spoken-name conclusions remain provisional, and contrast ratios are estimates from compressed video. This project does not certify app-wide WCAG conformance.

## Explore the project

| Resource | Access |
| --- | --- |
| Live report | [site link] |
| PDF report | [Download the audit](public/reports/PickMe_Audit_Part1.pdf) |
| Evidence package | [Screenshots, audio excerpts, and data](public/downloads/PickMe_Audit_Evidence.zip) |
| Recorded walkthrough | [Watch on YouTube](https://www.youtube.com/watch?v=vrg4xJkxvxs) |
| Findings data | [JSON](data/findings.json) · [CSV](data/findings.csv) |
| Coverage matrix | [All 72 subtopics](data/subtopic_coverage.csv) |

## Why this project

Transport services depend on users being able to identify actions, enter locations, and understand the information needed to continue. Unclear spoken names or faint text can introduce uncertainty at these steps.

This audit investigates those barriers in a recorded exploration of PickMe, connects the evidence to relevant accessibility criteria, and proposes practical improvements and retest steps.

## Research method

**Research design:** descriptive single-app case study.  
**Evaluation method:** standards-based accessibility inspection.  
**Analysis:** qualitative interface and speech review, supported by descriptive contrast measurements and machine-assisted transcription.

The evidence set consists of a supplied Android package, a home-screen screenshot, and a user-recorded TalkBack walkthrough of approximately **9 minutes 40 seconds**.

1. Establish the app version, device, and evidence boundaries.
2. Inspect package metadata and bundled layout resources. Static inspection alone does not establish runtime accessibility failures.
3. Review sampled video frames and targeted screen details to trace navigation, focus, and visible content.
4. Review machine-transcribed speech in relation to focused controls. Two transcription passes support repeated patterns; exact identifier wording remains approximate.
5. Estimate text/background contrast from selected video-frame pixels using WCAG relative luminance calculations.
6. Assign finding IDs, distinguish severity from confidence, map candidate WCAG criteria, and document recommendations and retests.

The standards framework is **WCAG 2.2 Level A/AA**, interpreted for native software using **WCAG2ICT**, alongside Android accessibility guidance. This was an inspection of supplied evidence, rather than a controlled participant usability study. No participant interviews or research themes are used as evidence of app defects.

## Test environment

| Item | Recorded setup |
| --- | --- |
| App | PickMe Android |
| Package | `com.pickme.passenger` |
| Version | `26.100.0-LkPrd` |
| Device | HONOR X7c, user reported |
| Android | 14, user reported |
| Assistive technology | TalkBack; version unknown |
| TalkBack settings | Not fully verified; element-ID speech requires a controlled retest |
| Audit date | 4 November 2026 |

## Key findings

**The detailed findings, screenshots, and timestamped video evidence are available on this site: [site link].**

| ID | Finding | Severity | Evidence status | Video |
| --- | --- | --- | --- | --- |
| ACC-001 | Account menu rows announce numbered identifiers instead of useful menu names | High · 3/4 | Provisional spoken-name finding | [04:22–05:13](https://www.youtube.com/watch?v=vrg4xJkxvxs&t=262s) |
| ACC-002 | Pickup and destination announcements lack useful field content | High · 3/4 | Provisional spoken-name finding | [09:00–09:23](https://www.youtube.com/watch?v=vrg4xJkxvxs&t=540s) |
| ACC-003 | Home announcements contain technical identifiers and extra focus stops | Medium · 2/4 | Usability observation; WCAG failure not established | [01:28–02:01](https://www.youtube.com/watch?v=vrg4xJkxvxs&t=88s) |
| ACC-004 | Destination-search text has approximately 2.41:1 contrast | Medium · 2/4 | Video-based estimate; original-image confirmation needed | [01:52](https://www.youtube.com/watch?v=vrg4xJkxvxs&t=112s) |
| ACC-005 | White “Check” text has approximately 1.69–2.12:1 contrast | Medium · 2/4 | Video-based estimate; original-image confirmation needed | [02:02](https://www.youtube.com/watch?v=vrg4xJkxvxs&t=122s) |

Severity describes potential impact and remediation priority. It does not measure confidence or establish a WCAG failure. The report uses a four-point scale: **1 Low, 2 Medium, 3 High, 4 Critical**. No Critical finding is reported.

## User impact and improvement priorities

Unclear names may make account actions and route fields difficult to identify through speech. Redundant announcements may increase listening effort. Low-contrast prompts and labels may be harder to read for people with low vision or reduced contrast sensitivity.

These impacts are analyst interpretations, not measured participant outcomes. The recording does not demonstrate that booking is impossible.

The main recommendations are to expose meaningful names and current values for account and route controls, group related icons and labels into coherent actions, reduce decorative focus stops, and improve text contrast. Confirm fixes with controlled assistive technology retests and original-image measurements.

## Coverage and limitations

| Coverage | What the evidence supports |
| --- | --- |
| Home | Partial exploration of service tiles, search, promotions, and tabs |
| Account | Menu exploration and provisional naming concerns |
| About and legal pages | Pages reached; heading navigation and reflow not fully verified |
| Notifications and Activities | Empty states observed; dynamic announcements unverified |
| Ride route entry | Initial pickup/destination controls reached; route entry not completed |
| Other journeys | Login/OTP, fare selection, booking, payment, cancellation, and other service flows not tested |
| Other configurations | Font scaling, magnification, landscape, keyboard, Switch Access, Voice Access, and other devices not tested |

All 12 requested categories appear in the coverage matrix: screen readers; navigation and interaction; visual access; touch; forms and input; dynamic content and feedback; information structure; maps and location; task completion; cognitive access; device and assistive technology compatibility; and compliance and reporting.

**Coverage is not a pass rate.** Unknown settings, interrupted speech, sampled frames, and video compression limit interpretation. No overall accessibility percentage is assigned. Candidate criteria include **4.1.2 Name, Role, Value**, **2.5.3 Label in Name**, **1.3.1 Info and Relationships**, and **1.4.3 Contrast (Minimum)**; the report explains the qualifications for each mapping.

## Interactive report

The website includes finding filters, enlarged evidence screenshots, audio excerpts, a searchable coverage matrix, and YouTube playback controls that start at relevant timestamps. Direct YouTube links provide an alternative to embedded playback.

The report presents the evidence as an interactive case study, with a PDF available for reference.

## Next steps

- Retest spoken names with element-ID speech disabled, if that setting is available, and capture accessibility-node names and values.
- Complete destination search and vehicle/fare selection before expanding to transactional journeys.
- Recheck contrast using original screenshots or design colours.
- Evaluate additional input modes, display settings, and devices.

## Author and attribution

**Tharindu Piyasena** · UX research and accessibility  
[GitHub](https://github.com/tharidupiyasena) · [Portfolio](https://tharidupiyasena.notion.site/)

This is an independent project and is not affiliated with or endorsed by PickMe. PickMe branding and Google Play promotional imagery belong to their respective owners. Promotional artwork provides product context; the audit findings use recorded test evidence. No APK or raw recording is distributed in this repository.

The work was prepared with AI assistance for transcription, analysis, and report production; its evidence limitations are documented above. No additional reuse licence is granted by this README.

## References

- [WCAG 2.2](https://www.w3.org/TR/WCAG22/)
- [WCAG2ICT: applying WCAG 2.2 to non-web ICT](https://www.w3.org/TR/wcag2ict-22/)
- [Android accessibility testing](https://developer.android.com/guide/topics/ui/accessibility/testing)
- [PickMe on Google Play](https://play.google.com/store/apps/details?id=com.pickme.passenger&hl=en)
