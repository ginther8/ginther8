# Wee Peng Fei

I'm a Computer Science student specialising in Real-Time Interactive Simulation at DigiPen / Singapore Institute of Technology. I build Android features, backend services and games using Kotlin, Go, C and C++.

## Project case studies

- [Runi](#runi) is my main project, an Android running app. I work on authentication, backend services and recording transfers.
- [WDYM there's no milopeng in space](#milopeng) shows my work on player progression and power-ups in C.
- [PRC Data Challenge 2026](#prc-challenge) shows my work on data exploration, model experiments and evaluation.

School-project source repositories are private under school restrictions. The PRC repository is public.

### Runi

*Ongoing university team project | Kotlin, Android SDK, Firebase Authentication, Go, PostgreSQL, C++*

Runi lets runners record an activity and race against recorded runs. I built backend services and Android integration for sign-in, uploads, run management and sharing. I also integrated a teammate's C++ run verifier with Go APIs and PostgreSQL to store verification results and determine which recordings could be shared.

Recording transfers needed to run off the Android UI thread, and retries needed to retain the correct owner after an account change. I moved transfers to a background executor, persisted the initiating account with each upload identity and rejected mismatched users. I wrote regression tests to check that the original owner could retry while a second account and unauthenticated attempts were rejected.

For downloads, I validated recording identity and course metadata before atomically replacing a cached file. I added Android tests for incompatible downloads, preservation of existing recordings and offline playback. The integrated workflow demonstrated uploading, sharing, downloading and replaying a recording between two accounts.

<a id="milopeng"></a>
### WDYM there's no milopeng in space

*University team project | C, CProcessing | 4-person team*

This is a 2D space shooter in which players gain experience points (XP) from defeating enemies and choose stat upgrades as they level up. Within a planned commitment of six hours per week, I implemented the XP bar, enemy XP drops, level-up screen, scaling XP thresholds and stat increments.

An XP award could exceed the next level threshold or earn multiple levels at once. I implemented carry-over logic so excess XP contributes towards the next level, and a queue that presents one upgrade choice for each level gained. This keeps earned progression from being lost or upgrade choices from being skipped.

I also implemented random spawning and collection for three power-up types: health recovery, temporary damage boosts and temporary attack-speed boosts. The completed progression features are recorded in our production backlog. Detailed test results and a specific debugging history are not available for this project.

<a id="prc-challenge"></a>
### PRC Data Challenge 2026

*Team competition project | Python, CatBoost, data exploration and evaluation*

Our team built a pipeline to predict aircraft taxi-out time at ten European airports. I inspected Parquet datasets for missing values and anomalies, ran CatBoost models including V2 with 15-minute traffic features, and tested feature variants through V6 ablation experiments. I also investigated weather features and the project's F3 modelling approaches.

I reproduced Exp04 and checked that the results matched the reference experiment before comparing further model runs. I examined root mean squared error (RMSE) and experiment logs to assess potential improvements. The team used held-out January and July 2025 data for validation. Some approaches did not improve results: the team documentation records that weather features were not retained and an ADS-B-first direct-model blend failed the July validation criterion.

My contribution focused on exploration, experiments, reproduction and evaluation. The final team pipeline combined its base model with additional corrections and post-processing, improving pooled validation RMSE from 334.05 to 306.27 seconds. Lower RMSE means smaller prediction errors; these figures describe the team pipeline rather than an improvement attributable to my work alone.

[View the public repository](https://github.com/ginther8/prc2026_vigorous-glove) · [Read the reproduction and validation guide](https://github.com/ginther8/prc2026_vigorous-glove/blob/main/README_adsb_pipeline.md)

## Additional project

### Revenge of YK

*University team project | C++, Alpha Engine | 4-person team*

Revenge of YK is a 2D typing game. I implemented real-time keystroke validation and character highlighting so players receive immediate feedback while typing. I also built an interactive tutorial that waits for the player to demonstrate each mechanic before advancing.

To support development, I built a debug console that pauses gameplay and lets the team spawn enemies and pickups and change difficulty and weather. My other contributions included collision and enemy-death effects, a player-death transition and layered parallax effects. These features are marked completed in the production backlog.

## Contact

[Connect with me on LinkedIn](https://www.linkedin.com/in/wee-peng-fei-1ab620240/)
