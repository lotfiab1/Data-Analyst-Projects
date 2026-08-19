
## Table of Contents

- [British Menagerie Period](#british-menagerie-period)
- [The Cicadas Are Coming](#the-cicadas-are-coming)
- [A Plant-Based Coffee Shop](#a-plant-based-coffee-shop)
- [The Ocean's Deep-Diving Animals](#the-oceans-deep-diving-animals)
- [Flight Delays](#flight-delays)
- [Is Granola Healthy?](#is-granola-healthy)
- [The Internet and Dating](#the-internet-and-dating)
- [Lion Attacks](#lion-attacks)
- [Art as Data](#art-as-data)
- [Plotting Animal Words](#plotting-animal-words)
- [Skeletal Variation](#skeletal-variation)
- [E-Bike Stopping Distances](#e-bike-stopping-distances)
- [A Century of Top Songs](#a-century-of-top-songs)
- [Tusked Elephants](#tusked-elephants)
- [Warm Waters off Peru](#warm-waters-off-peru)
- [Our World Connected](#our-world-connected)

---

## Projects Overview

### British Menagerie Period

- **Folder:** [any animals except project](./any-animal-except-project)
- **Primary Notebook:** `any-animal-except-project.ipynb`
- **Technologies:** `Python`, `Pandas`, `Matplotlib`
- **Dataset:** `animal-word-trends-menageries.csv` — 3,906 rows tracking the yearly print-frequency (per million words) of animal words from 1700 to 2019.
- **Objective:** Investigate whether the exhibition of exotic animals in British menageries (1750–1835) influenced how often their names appeared in print.

#### Workflow

- Data loading and initial exploration
- Grouping/aggregation to find the most-trending animal word per year
- Reusable plotting function to compare word-frequency trends across the menagerie period
- Comparative analysis across three animal groups (easy-to-exhibit menagerie animals, difficult-to-keep animals, and later-imported Australian animals)

#### Key Findings & Insights

- "Tiger" was the most frequently trending animal word in 318 of 320 years analyzed.
- Easily-exhibited menagerie animals (tiger, hyena, tapir, toucan, macaw, ostrich) all show a rise in word frequency starting around 1750, coinciding with the start of the menagerie period.
- Animals that were difficult to keep in captivity (hummingbird, chimpanzee, meerkat, penguin) showed little change in usage frequency over the same period, supporting the hypothesis that exhibition (not just general animal interest) drove word popularity.
- Among Australian animals introduced from the 1780s, kangaroo and wombat word usage rose with exhibition, while koala's frequency barely increased, suggesting it was harder to exhibit.

---

### The Cicadas Are Coming

- **Folder:** [cicadas are coming project](./cicadas-are-coming-project)
- **Primary Notebook:** `cicadas_are_coming_project.ipynb`
- **Technologies:** `Python`, `Pandas`, `Matplotlib`
- **Dataset:** `animal-word-trends-cicada.csv` (word frequency 1820–2020) and `cicada-brood-mentions-print.csv` (total print mentions per brood, 1915–1970).
- **Objective:** Form and test a hypothesis about which periodical cicada brood (13-year vs. 17-year lifecycle) receives the most public/media attention, using historical word-usage data.

#### Workflow

- Data loading and reusable plotting function for word trends
- Visual hypothesis formation by overlaying known brood emergence years on the "cicada" word-frequency trend
- Hypothesis testing against an independent dataset of actual print mentions per brood
- Bar chart comparison of brood mention counts

#### Key Findings & Insights

- Word usage for "cicada" shows periodic peaks that align more closely with a 17-year cycle than a 13-year cycle.
- Visual overlay of emergence years suggested Brood II and Brood X were the most prominent 17-year broods.
- The actual mentions dataset confirmed this: Brood II had the highest print mentions (1,024), followed by Brood X (968), while Brood XIV had far fewer (636).
- The quantitative mention data validated the hypothesis formed from visual inspection of the word-usage trend.

---

### A Plant-Based Coffee Shop

- **Folder:** [coffee survey project](./coffee-survey-project)
- **Primary Notebook:** `coffee_survey_project.ipynb`
- **Technologies:** `Python`, `Pandas`, `Matplotlib`
- **Dataset:** `coffee-survey-results.csv` — survey responses from approximately 1,170 coffee drinkers, including dairy and sweetener preference columns.
- **Objective:** Identify the most popular dairy alternatives and sweeteners among coffee drinkers to recommend a stocking strategy for a new plant-based specialty coffee shop.

#### Workflow

- Data loading and column selection/renaming for readability
- Missing-value handling (`dropna()` on skipped survey branches)
- Calculation of preference percentages via column means
- Horizontal bar chart visualization of dairy and sweetener preferences

#### Key Findings & Insights

- Among plant-based dairy options, oat milk was the most preferred (~38.8% of respondents), followed by almond milk (~10.3%) and soy milk (~5.7%); whole milk remained the overall most popular dairy choice (~56.2%).
- Granulated sugar was the dominant sweetener choice (~63.9%), followed by brown sugar (~26.5%) and raw sugar (~24.5%).
- Recommendation: stock oat milk as the primary plant-based dairy alternative, and ensure granulated sugar, honey, and an artificial sweetener are readily available.

---

### The Ocean's Deep-Diving Animals

- **Folder:** [deepest divers project](./deepest-divers-project)
- **Primary Notebook:** `deepest_divers_project.ipynb`
- **Technologies:** `Python`, `Pandas`, `Matplotlib`
- **Dataset:** `deepest-diving-animals.csv` — deepest recorded diving depths (in meters) for 118 marine animal species across 10 categories.
- **Objective:** Compare diving depths across marine animal categories and demonstrate techniques for turning a default Matplotlib bar chart into a compelling, storytelling visualization.

#### Workflow

- Data loading and category-level aggregation (`groupby().max()`)
- Iterative bar chart refinement: horizontal bars, sorting, removing spines, adding faded gridlines
- Adding contextual reference bars (e.g., submarine implosion depth, Titanic resting depth) with custom coloring
- Extension analyses on penguin-specific depths and animals diving beyond 1,000 meters

#### Key Findings & Insights

- Toothed whales are the deepest-diving category, with a maximum recorded depth of 2,992 meters, followed by seals (2,389 m) and turtles (1,344 m).
- The Emperor Penguin is the deepest-diving penguin species at 564 meters — deeper than the maximum recorded depth for "other seabirds" (152 m).
- Only three animal categories (turtles, seals, toothed whales) dive deeper than the reference depth of a submarine implosion (730 m).
- Several toothed whale species (e.g., Sperm Whale, Northern Bottlenose Whale) approach or exceed depths comparable to the Titanic's resting depth (3,800 m).

---

### Flight Delays

- **Folder:** [flight delays project](./flight-delays-project)
- **Primary Notebook:** `flights_delays_project.ipynb`
- **Technologies:** `Python`, `Pandas`, `Matplotlib`
- **Dataset:** `flights.csv` — 5,000 domestic flight records departing Atlanta airport in 2023, with scheduled/actual departure times. Extension uses `us-daily-passengers.csv` (365 days of national passenger volume).
- **Objective:** Determine how the day of the week affects the likelihood of a flight departure delay, and whether passenger volume helps explain the pattern.

#### Workflow

- Data loading and datetime conversion of scheduled/actual departure columns
- Feature engineering: computing delay duration and a boolean "is_late" flag (>15 minutes late)
- Extraction of day-of-week and aggregation of delay percentage by day
- Bar chart visualization, reordered into calendar day sequence
- Extension: merging in daily passenger volume data and visualizing both series on a dual-axis chart

#### Key Findings & Insights

- Tuesday had the lowest delay percentage (~15.4%), while Sunday had the highest (~23.4%).
- Sundays, Mondays, and Fridays had both the highest delay percentages and the highest average passenger volumes, while Tuesdays and Wednesdays had the lowest of both.
- A positive correlation was observed between daily passenger volume and delay percentage, suggesting that higher travel demand contributes to more flight delays.

---

### Is Granola Healthy?

- **Folder:** [granola healthy project](./granola-healthy-project)
- **Primary Notebook:** `granola_healthy_project.ipynb`
- **Technologies:** `Python`, `Pandas`, `Matplotlib`
- **Dataset:** `healthy-food-survey-public.csv` and `healthy-food-survey-experts.csv` — public and expert survey responses on whether each of 40 foods is considered healthy.
- **Objective:** Visualize how closely public opinion and expert opinion align on which foods are healthy, using paired-data scatter plot techniques.

#### Workflow

- Data loading and cleaning (converting yes/no/no_opinion counts into a percentage-healthy score) for both datasets
- Merging public and expert datasets on food name
- Scatter plot construction with progressive refinement: adding a 1:1 equality reference line, squaring the aspect ratio, adjusting marker transparency
- Labeling outlier points and points of strong agreement/disagreement

#### Key Findings & Insights

- Apples were rated healthy by 96% of the public and 99% of experts; white bread was rated healthy by only 20% (public) and 15% (experts) — an area of strong consensus.
- The largest public/expert disagreement was for granola bar (public 70% vs. experts 28%, a 42-point gap), followed by coconut oil, frozen yogurt, and granola.
- Foods like tofu, sushi, quinoa, and hummus were rated notably healthier by experts than by the public (experts_minus_public gaps of 25–31 points).
- Foods such as chicken, cheddar cheese, and baked potatoes showed the closest public/expert agreement (differences of 0–1 percentage points).

---

### The Internet and Dating

- **Folder:** [how couples met project](./how-couples-met-project)
- **Primary Notebook:** `how-couples-met-project.ipynb`
- **Technologies:** `Python`, `Pandas`, `Matplotlib`, `Seaborn`
- **Dataset:** `how-couples-met.csv` — percentage of couples who met via each of 7 methods (college, work, friends, family, online, restaurant, neighbors), by decade from the 1960s to 2010s.
- **Objective:** Investigate how the internet has changed the way couples meet, and demonstrate multi-line graph storytelling techniques.

#### Workflow

- Data loading and setting decade as the time-series index
- Baseline multi-line plot using pandas' built-in `.plot()`
- Progressive visual refinement: highlighting a focus line (online) with color/thickness, dimming other lines, direct end-of-line labeling instead of a legend, removing spines, adding faded gridlines
- Extension: horizontal bar plots (via Seaborn) comparing meeting methods within and across decades (1960s vs. 2010s)

#### Key Findings & Insights

- Meeting online rose from 0% in the 1960s–70s to 42.2% by the 2010s, becoming the single most common way couples meet.
- Meeting "through friends," historically the top method (45.9% in the 1960s), declined to 28.9% by the 2010s.
- Meeting "through family" fell from 30.4% in the 1960s to just 10.0% in the 2010s.
- Side-by-side decade comparisons visually confirm the dramatic shift away from traditional in-person introductions toward online meeting.

---

### Lion Attacks

- **Folder:** [lion attacks project](./lion-attacks-project)
- **Primary Notebook:** `lion-attacks-project.ipynb`
- **Technologies:** `Python`, `Pandas`, `Matplotlib`, `Scikit-learn`
- **Dataset:** `lion-attacks-lunar-cycle.csv` (30 days of the lunar cycle, evening moonlight level, and attack counts) and `lion-belly-sizes.csv` (lion belly-size estimates by moonlight level, averaged over 11,000 sightings).
- **Objective:** Investigate whether evening moonlight influences lion hunting activity and attacks on humans, and assess evidence for a causal (not just correlational) relationship.

#### Workflow

- Data loading and scatter plot visualization of attacks vs. moonlight
- Linear regression modeling (custom `LinearModel` class using scikit-learn) with goodness-of-fit (R²) reporting
- Independent supporting-evidence analysis using lion belly-size data as a proxy for hunting success
- Extension: using the fitted model to predict attack counts at specific moonlight levels and compute percentage change

#### Key Findings & Insights

- Lion attacks show a negative linear relationship with evening moonlight (slope = -8.92, R² = 0.475): the model predicts about 11.65 attacks at zero moonlight vs. 2.74 at full moonlight, a 76.52% decrease.
- Lion belly size (a proxy for hunting success) also shows a negative relationship with moonlight (slope = -0.03, R² = 0.682), with a stronger fit than the attacks model.
- Because two independent datasets show the same negative relationship, combined with a plausible mechanism (prey can see and avoid lions more easily in bright moonlight), the evidence supports a causal — not merely correlational — link between moonlight and reduced lion hunting success.

---

### Art as Data

- **Folder:** [mondrian art project](./mondrian-art-project)
- **Primary Notebook:** `mondrian-art-project.ipynb`
- **Technologies:** `Python`, `Pandas`, `Matplotlib`
- **Dataset:** `mondrian-painting-features.csv` (3,204 geometric feature rows across paintings) and `mondrian-painting-info.csv` (136 paintings, 1920–1940, with year/title/dimensions). A disputed painting's features are in `fp26-features.csv`.
- **Objective:** Represent Piet Mondrian's paintings as tabular geometric data to analyze his artistic evolution and evaluate whether a disputed 1926 painting could be a forgery.

#### Workflow

- Data loading and exploration of painting feature records
- Custom function to reconstruct/draw a painting from its rectangle/line feature data
- Feature engineering: quantifying painting "complexity" as feature count per painting
- Merging complexity data with painting metadata to plot complexity vs. year
- Forgery detection by comparing a disputed painting's complexity against the distribution of authenticated paintings from the same era
- Extensions: analyzing painting dimensions (width/height/area) over time and tracking percentage color usage (blue, red, yellow, white, black, gray) over time

#### Key Findings & Insights

- Painting complexity (feature count) increases noticeably after 1935, indicating a shift in Mondrian's style toward more complex compositions later in his career.
- A disputed 1926 painting (`fp26`) has a complexity of 54 features, a clear outlier compared to authenticated paintings from that same year — evidence suggesting it may be a forgery.
- Painting dimensions show no strong overall trend over time, though there is greater variability (including some very large canvases) after 1935.
- White consistently dominates the color palette across Mondrian's paintings; primary colors (blue, red, yellow) vary by individual composition rather than following a clear time trend.

---

### Plotting Animal Words

- **Folder:** [plotting animal words project](./plotting-animal-words-project)
- **Primary Notebook:** `plotting-animal-words-project.ipynb`
- **Technologies:** `Python`, `Pandas`, `Matplotlib`
- **Dataset:** `animal-word-trends-intro.csv` — 3,145 rows of yearly word frequency (per million words) for various animal words, spanning 1700–2019.
- **Objective:** Practice forming and testing hypotheses about historical animal word usage, connecting word-frequency trends to real-world technological and societal events.

#### Workflow

- Data loading and construction of a reusable word-trend plotting function
- Single- and multi-word trend comparisons (e.g., horse vs. automobile invention, penguin vs. dinosaur)
- Hypothesis exploration around the completion of the US transcontinental railway (1869) across four animal words
- Extension comparing long-term "cat" vs. "dog" word usage trends

#### Key Findings & Insights

- "Horse" usage shows a brief increase then a large decline following the invention of the automobile (1886), consistent with reduced reliance on horses for transport.
- "Penguin" is used roughly 3 times more frequently in print than "dinosaur."
- "Lobster" word usage shows a sharp increase after the 1869 transcontinental railway completion, suggesting improved rail transport may have boosted its popularity/availability.
- "Dog" has maintained roughly a 2:1 usage lead over "cat" over the past 300 years, with both words seeing a sharp rise in mentions starting around 1970.

---

### Skeletal Variation

- **Folder:** [skeletal](./skeletal)
- **Primary Notebook:** `skeletal-variation.ipynb`
- **Technologies:** `Python`, `Pandas`
- **Dataset:** `adult-human-skeleton.csv` (206 human bones), `mammal-neck-bones.csv` (302 mammal species), `bird-neck-bones.csv` (81 bird species).
- **Objective:** Explore variation in skeletal structure — both within the human body and across mammal and bird species — and test common claims about bone counts.

#### Workflow

- Data loading and region-based aggregation of human bone counts
- Verification of the claim that over half of human bones are in the hands and feet
- Analysis of bone fusion from infancy (`fused_from` column) to determine infant bone count
- Cross-species comparison of neck vertebra counts for mammals and birds, including bar chart visualization of bird neck vertebra distribution
- Extensions: identifying birds with fewest neck vertebrae, comparing human arm vs. leg bone counts, and counting human ribs

#### Key Findings & Insights

- 51.5% of the 206 adult human bones are located in the hands (54) and feet (52), confirming the popular claim.
- Human infants have 305 bones, which fuse down to 206 in adulthood (e.g., the sternum forms from the fusion of 6 separate bones).
- Nearly all 302 mammals in the dataset have exactly 7 neck vertebrae — including giraffes — with only sloths (6 or 9) and the West Indian manatee (6) as exceptions.
- Birds show far more variation in neck vertebrae (10–23), with the Mute Swan having the most (23) and the Blue-and-Yellow Macaw the fewest (10).
- Humans have 8 leg bones vs. 6 arm bones, and 24 ribs (12 pairs).

---

### E-Bike Stopping Distances

- **Folder:** [stopping distances project](./stopping-distances-project)
- **Primary Notebook:** `stopping-distances-project.ipynb`
- **Technologies:** `Python`, `Pandas`, `Matplotlib`, `Scikit-learn`
- **Dataset:** `ebike-stopping-distances.csv` (9 speed/distance measurements), plus `ebike-data-low-speed.csv`, `ebike-data-high-speed.csv`, and (in the extension) `car-stopping-distances.csv`.
- **Objective:** Model the relationship between speed and stopping distance for e-bikes (and cars, as an extension), comparing linear vs. quadratic model fit.

#### Workflow

- Data loading and scatter plot visualization of speed vs. stopping distance
- Linear regression modeling (custom `LinearModel` class) with R² evaluation
- Physical sanity-checking of the model (checking predicted distance at zero speed)
- Incorporating low-speed data and fitting a `QuadraticModel` (via scikit-learn `PolynomialFeatures`)
- Validating the quadratic model against unseen high-speed data
- Extension: repeating the linear vs. quadratic comparison on car stopping-distance data

#### Key Findings & Insights

- A linear model fit the original e-bike data well (R² = 0.968) but predicted an implausible negative stopping distance at zero speed.
- Incorporating low-speed data and fitting a quadratic model improved the fit (R² = 0.989) and better matched the physical expectation that stopping distance approaches zero as speed approaches zero.
- The quadratic model, though only trained on data up to ~36 km/h, extrapolated reasonably well to unseen high-speed data (up to 61 km/h).
- For car stopping-distance data, the quadratic model again outperformed the linear model (R² = 0.981 vs. 0.925), consistent with the physics of kinetic energy (KE = ½mv²) scaling quadratically with speed.

---

### A Century of Top Songs

- **Folder:** [top songs project](./top-songs-project)
- **Primary Notebook:** `top-songs-project.ipynb`
- **Technologies:** `Python`, `Pandas`, `Matplotlib`
- **Dataset:** `top-song-durations.csv` — the number-one hit song for each year from 1923 to 2023 (101 records), including artist, title, and duration.
- **Objective:** Determine whether number-one hit song durations have changed over the past century, and identify any notable historical shifts.

#### Workflow

- Data loading and type conversion
- Parsing duration strings (HH:MM:SS) into numeric total-seconds values via string splitting
- Time-series visualization of song duration by year
- Identifying minimum/maximum duration outliers
- Extension: comparing average song duration before and after a key inflection point (1968)

#### Key Findings & Insights

- The shortest-ever number-one hit was "Sonny Boy" by Al Jolson (1928) at 1 minute 55 seconds; the longest was "Hey Jude" by The Beatles (1968) at 7 minutes 11 seconds.
- "Hey Jude" created a sharp spike in the duration trend, roughly twice as long as any prior number-one hit.
- Average top-hit duration increased from about 172.6 seconds (2:53) before 1968 to about 226.8 seconds (3:47) after 1968 — an increase of roughly 31%, indicating a lasting shift rather than a one-off outlier.

---

### Tusked Elephants

- **Folder:** [tusked elephants project](./tusked-elephants-project)
- **Primary Notebook:** `tusked-elephants-project.ipynb`
- **Technologies:** `Python`, `Pandas`, `Matplotlib`, `Scikit-learn`
- **Dataset:** `male-elephant-tusk-size.csv` — 299 records of elephant age, shoulder height, and tusk length, split into a pre-poaching cohort (1966–68) and a post-recovery cohort (2005–13).
- **Objective:** Assess whether the ivory-poaching period of the 1970s–80s had a lasting genetic impact on elephant tusk size.

#### Workflow

- Data loading and splitting into pre-poaching and post-recovery subsets
- Naive comparison of average tusk length between periods
- Controlling for the confounding variable of body size via a tusk-length-vs-shoulder-height scatter plot
- Linear regression modeling (custom `LinearModel` class) fit separately to each period, with slope/R² comparison
- Extension: using both models to predict tusk length at specific shoulder heights and compute percent differences

#### Key Findings & Insights

- Raw average tusk length dropped from 67.4 cm (pre-poaching) to 58.0 cm (post-recovery), but this comparison is confounded by elephant age/size.
- After controlling for shoulder height, the pre-poaching model slope (0.83, R² = 0.831) is much steeper than the post-recovery model slope (0.40, R² = 0.431), indicating a genuine shift in the tusk-length-to-body-size relationship, not just younger elephants in the later sample.
- At a shoulder height of 250 cm, pre-poaching elephants are predicted to have tusks about 49% longer than post-recovery elephants of the same size — evidence consistent with selective poaching pressure reducing tusk size in surviving lineages.

---

### Warm Waters off Peru

- **Folder:** [warm waters peru project](./warm-waters-peru-project)
- **Primary Notebook:** `warm-waters-peru-project.ipynb`
- **Technologies:** `Python`, `Pandas`, `Matplotlib`
- **Dataset:** `animal-word-trends-peru.csv` (word frequency for 5 fish species) and `anchoveta-caught-per-year.csv` (annual anchoveta catch in megatonnes, 1950–1990).
- **Objective:** Investigate the relationship between El Niño events and word-usage trends for economically important Peruvian fish species, and explain the underlying mechanism.

#### Workflow

- Data loading and reusable plotting function marking known El Niño years (1965, 1973, 1983, 1987)
- Comparative trend analysis across five fish words (sardine, mackerel, bonito, anchoveta, hake)
- Multiple-hypothesis generation (abundance, scarcity, exception hypotheses) for the "anchoveta" pattern
- Cross-referencing word trends against actual annual catch-size data
- Extension: quantitative comparison of average word frequency during vs. outside El Niño years, normalized overlay plot of word frequency vs. catch size, and a written research report

#### Key Findings & Insights

- Of the five fish words tested, only "anchoveta" showed a consistent increase in usage during El Niño years (~8-10% above its average in other years); the other four words were flat or slightly lower.
- Anchoveta catch size grew from near zero in 1950 to a peak of over 17 megatonnes in 1970, then collapsed by roughly 90% within three years, bottoming out around the 1973 El Niño event, with a second severe collapse (to 0.36 megatonnes) after the 1983 event.
- Word usage for "anchoveta" tends to rise gradually in the two-to-three years before an El Niño event, while the catch collapse itself is sudden and concentrated in the event year — supporting the "scarcity hypothesis" (warm water disrupts cold-water upwelling that anchoveta depend on).

---

### Our World Connected

- **Folder:** [world connected project](./world-connected-project)
- **Primary Notebook:** `world-connected-project.ipynb`
- **Technologies:** `Python`, `Pandas`, `NumPy`, `Matplotlib`
- **Dataset:** `world-internet-users.csv` (global internet users, 1990–2024) and `historical-world-population.csv` (population estimates back to 10,000 BCE). Extension uses continent-level breakdowns from `extension-internet-users-by-continent.csv` and `extension-historical-population-by-continent.csv`.
- **Objective:** Track the growth of global internet adoption over time and determine when the world crossed key adoption milestones, both globally and by continent.

#### Workflow

- Data loading and merging of internet-user and population datasets on year
- Missing-value handling (dropping years without matching population data)
- Feature engineering: calculating percent of world population connected to the internet per year
- Time-series visualization with a 50%-threshold reference line
- Threshold detection (first year surpassing 50% connectivity)
- Extension: merging and analyzing continent-level internet adoption, including per-continent trend lines and bar chart comparisons of adoption percentage vs. population size

#### Key Findings & Insights

- Global internet adoption grew from 3 million users (0.06% of the population) in 1990 to over 5.3 billion users (66.07%) by 2022.
- The world first crossed 50% internet connectivity in 2019 (53.69%).
- North America was the first continent to reach 50% adoption (2006), followed by Oceania (2007), Europe (2008), South America (2013), and Asia (2020); Africa had not yet reached 50% adoption as of the most recent data (39% in 2021).
- Asia has by far the largest population (4.72 billion) and the largest absolute number of internet users among continents, despite a comparatively moderate adoption percentage (58%).
