---
license: cc-by-4.0
pretty_name: Subskills sports technique taxonomy
language:
- en
tags:
- sports
- taxonomy
- skill-learning
- coaching
- education
- tutorials
size_categories:
- n<1K
configs:
- config_name: sub_skills
  data_files: sub_skills.csv
  default: true
- config_name: sports
  data_files: sports.csv
- config_name: sub_skill_stats
  data_files: sub_skill_stats.csv
---

# Subskills sports technique taxonomy

22 sports broken down into 554 sub-skills, the individual techniques people actually practice, like the backhand clear in badminton or the back-rank mate in chess. Each sub-skill has a short description and a place in a suggested learning order, plus counts of the tutorial videos reviewed for it on [Subskills](https://subskills.xyz).

Snapshot: 2026-09-30.

The same data is on [GitHub](https://github.com/ihvou/subskills-taxonomy), [Hugging Face](https://huggingface.co/datasets/subskills/sports-technique-taxonomy) and [Kaggle](https://www.kaggle.com/datasets/subskills/sports-technique-taxonomy).

**Sub-skills per sport:** Badminton 32, Boxing 23, Brazilian jiu-jitsu 39, Chess 30, Climbing 24, Cycling 25, Golf 27, Gym (men) 28, Gym (women) 24, Muay Thai 32, Padel 24, Pickleball 21, Pilates 21, Running 27, Skiing 21, Snowboarding 20, Soccer (Individual Skills) 21, Surfing 24, Swimming 22, Table tennis 24, Tennis 23, Yoga 22.

## Files

| File | Rows | Contents |
|---|---|---|
| `sub_skills.csv` | 554 | The sub-skills with their descriptions, learning order and level |
| `sports.csv` | 22 | The sports |
| `sub_skill_stats.csv` | 554 | Tutorial counts per sub-skill |
| `taxonomy.json` | | The sports and sub-skills again, nested |

## Columns

**sub_skills.csv**

| Column | Meaning |
|---|---|
| `sport`, `sub_skill` | Identifiers (slugs) |
| `name`, `description` | The sub-skill's name and a one-line description |
| `learning_order` | Suggested order to learn the sub-skills of a sport, starting at 1 |
| `difficulty` | The learning order scaled from 1 to 5 within each sport: the first sub-skill is 1 and the last is 5 |
| `level` | `beginner` for difficulty up to 2.33, `intermediate` up to 3.67, `advanced` above |
| `url` | The sub-skill's page on subskills.xyz |

**sports.csv**: `sport`, `name`, `sub_skills` (how many), `url`.

**sub_skill_stats.csv**

| Column | Meaning |
|---|---|
| `videos_published` | Tutorials currently shown on the sub-skill's page |
| `videos_rejected` | Tutorials that were reviewed for the sub-skill and turned down |
| `published_beginner`, `published_intermediate`, `published_advanced` | Published tutorials by level |
| `published_youtube`, `published_tiktok`, `published_instagram` | Published tutorials by platform |

## How it's made

The sub-skills were researched sport by sport and put into a teaching order, so `learning_order` 1 is what a beginner should learn first.

Every tutorial is reviewed before it's published: how squarely it covers the sub-skill, in that sport, and how well it teaches it. `videos_rejected` counts the tutorials that were reviewed and turned down, usually because they cover a different technique or a different sport, or teach little. A video can be reviewed for more than one sub-skill, so counts are per sub-skill, not per video.

Across the snapshot: 39,456 tutorials reviewed, 21,556 published and 17,900 rejected (45%). Of the published ones, 45% are for beginners, 41% intermediate and 13% advanced.

The dataset contains no videos, video titles or transcripts. Those belong to their creators.

## License

[CC BY 4.0](LICENSE). You can use, share and adapt the data for any purpose, including commercially, as long as you credit Subskills with a link, for example:

> Sports taxonomy from [Subskills](https://subskills.xyz), CC BY 4.0

## See also

- The website: [subskills.xyz](https://subskills.xyz)
- The code for the website and iOS app: [github.com/ihvou/subskills](https://github.com/ihvou/subskills)
