# Requirements Specification

## User Characteristics

There are two user groups interested in this project:

- **Map Designer**: A technically versed person using Windows or OSX which has knowledge of GIS
software but not necessarily of it's inner technical workings.
- **System Administrator**: The person who needs to host the published maps.

## Actors and Stakeholders


## Non Functional Requirements

The most important NFR in this scenario is usability. If we cannot get usability right
no one will use our solution.

### Usability

#### Learnability

Map designers should not have to learn how to use the command line in order to use Docker.

### Repeatable

Generating OSM vector tiles must be possible any time because OSM updates regularly.

### Performance

The tileserver needs to be reasonably fast but not highly performant.

TODO: Tell numbers
