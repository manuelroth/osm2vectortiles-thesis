# Requirements Specification

## User Characteristics

There are two user groups interested in this project:

- **Map Designer**: A technically versed person using Windows or OSX which has knowledge of GIS
software but not necessarily of it's inner technical workings.
- **System Administrator**: The person who needs to host the published maps.

## Actors and Stakeholders

## Use Cases

NOTE: I actually found use cases to be not so useful in SE2 project. But somehow this project
is not as "imaginable" as a web application. Perhaps short uses cases are still a good idea.

But perhaps this should be done more in the form of user stories (a bit more informal).

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
