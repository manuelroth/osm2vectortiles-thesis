# Meeting Protocol {.unnumbered}

## 7th September 2015 {.unnumbered}

**Participants**

- Petr Pridal
- Stefan Keller
- Lukas Martinelli
- Manuel Roth

**Talking points**

- Get to know each other
- Project goal
- Architecture of Docker containers
- Definition of tasks and milestones

## 16th September 2015 {.unnumbered}

**Participants**

- Stefan Keller
- Lukas Martinelli
- Manuel Roth

**Talking points**

- Language choice of thesis
- Similarity of documentation to SE2 project
- Role of Petr Pidal
- Mechanics of MBTiles

**Protocol**

- Create a project proposal.
- Inform ourselves about Meta Tiles
- Few prerendered tiles can cover most of the used map
- Thesis of prior years can be found at HSR eprints
- Before each meeting, send email with done, difficulties and plan for next week to Stefan Keller

**Questions and Answers**

- Can the thesis be written in English?
*Yes, that's up to you. Other groups did write their project documentation in English and the actual thesis in German.*

- Should the documentation be made similar to SE2?
*Yes, but only the parts with make sense to your project. Usually, the thesis is divided into two parts, the first part should be like an article of a computer magazine (C't). The second part all formal documents (requirements analysis, domain analysis, use cases)*

- What's Mr.Pridal's role? - Does Mr.Pridal affect the evaluation?
*Mr.Pridal can basically be viewed as an industrial partner. I will seek his opinion at the end of the project. If there should be differences between you and him, I will have the final word.*

## 25th September 2015 {.unnumbered}

**Participants**

- Stefan Keller
- Lukas Martinelli
- Manuel Roth

**Done**

- Went through OSM Workflow ( OSM Source -> Import OSM Data -> Postgis -> Source Project -> Export mbtiles -> Serving mbtiles)

**Difficulties**

- It was not clear, if we could take an existing source project or if we had to make our own.

**Plan**

- Documenating OSM Workflow
- Comparing osm2pgsql and imposm3
- Meeting with Petr Pridal on Monday

**Talking points**

- Imposm3 or osm2pgsql vor import: many people in the OSM community are used to osm2pgsql and its default schema(point, line, polygon, road). The criteria for choosing the import tool, should be efficenty and possiblity to update data with OSM diff files.
- Thesis should compare geopackages and mbtiles 
- Term feature set is more accurate than layer

## 28th September 2015 {.unnumbered}

**Participants**

- Petr Pridal
- Lukas Martinelli
- Manuel Roth

**Done**

- Reached alpha milestone(first version of components)

**Difficulties**

- We need to define system requirements for the containers
  - On small machines(> 500 RAM) null pointer exceptions while importing with imposm3
- What is the purpose of the debug viewer

**Plan**

- Next meeting with Petr: Monday 5pm, 19th of October 2015
- Decision of which rendering and tile serving stack should be choosen (based on performance tests with each stack)

**Talking points**

- Can current software stack meet our requirements?
	- Requirements osm2vectortile stack: Render whoule planet in reasonable amount of time(less than one month)
	- Requirements tileserver: not yet defined
- Performance:
	- Compare Vector tile rendering stack with wikimedia's
		- Import only necessary data for rendering
		- Compare your source project with wikimedia's
		- Why did wikimedia fork mapbox's osm-brigt style?
	- Tileserver: Compare performance of node + nginx with apache + renderd
- The debug viewer is needed, if you want to view the mbtiles without Mapbox studio
	- Petr would be interested to integrate thiw viewer into tileserver-php
- Rename tileserver to vtileserver for clarity

## 2th October 2015 {.unnumbered}

**Participants**

- Stefan Keller
- Manuel Roth

**Done**

- Documented OSM worklow
- Meeting with Petr
- OSM Planet file imported
- Passed alpha milestone

**Difficulties**

- OSX postgres volume mounting problem

**Plan**

- Compare Wikimedia OSM stack with current stack (performance)
- Decision of which rendering and tile serving stack should be choosen (based on performance tests with each stack)

**Questions and Answers**

- How many hours does each of us has to invest into the thesis?
*Every team member has to invest at least 240h into the thesis (8 ECTS * 30h)*

- On which server can we generate the mbtiles and how up-to-date should they be? (weekly updates)
*You can use the IFS server for the mbtiles generation. If there are problems with the server, please contact Mirko Stocker. There are no special requirements for how current the mbtiles have to be*

**Talking points**

- Mr. Keller creates the project proposal and sends it for review back to us. On next weeks meeting we are going to sign the project proposal.
- Mr. Keller's contact person at wikimedia maps: Tim alias Kolossos (tim@alder-digital.de)
