# Milestone Tasks

## Abstract
This document outlines tasks which need to be completed for milestones. Tasks
are listed by numbers and subsections, but these are just to allow for easy
reference and do not indicate required task completion order.

## `1.0.0a`

### Research and design

#### To do
1. Godot client/server handling
    1. Design communication protocol which is sent over websocket
2. Research iterations of chaoticgame.com website
3. Research iterations of chaoticgame.com game clients (desktop and unity web clients)

#### Completed
None

### Implementation

#### To do
1. Implement communication protocol. Depends on R&D section 1.1 of 1.0.0a tasklist

#### Completed
None

## Terminology
* R&D - Research and design

## Versioning
A version will look like `X.Y.Zl` (e.g. `1.5.2f`) where `X`, `Y`, and `Z` are numbers and `l` is a letter.

Numbers will used as follows:

`X` - Major version number. This will be incremented when major changes are made which may require the users or server maintainers to learn a new method of doing something, or if old features have been removed in favor of newer ones.

`Y` - Minor version number. This will be incremented when minor changes are made which do not add or remove any specific features, but may indicate that some features work a little differently. Existing features may have new functionality that has been added for various reasons.

`Z` - Revision version number. This will be incremented when bugs are fixed or small adjustments have been made which do not change the way a user interacts with the client.

Letters which can be used and their definitions are as follows:

`a` - Alpha - Initial builds for a version. These are likely buggy and feature-incomplete. They will not be allowed to connect to public servers as they are not stable.

`b` - Beta - All major features for a version are implemented per the task list for that version. The features have not been well-tested, however, and may still be buggy. These releases may not be allowed to connect to public servers as the features are not stable.

`r` - Release Candidate - All features from the task list have been implemented and tested. This release will be allowed to connect to RC servers for further public testing. If no further issues have been found, this may become the final release.

`f` - Final - Final release for the version. This has been well tested and has been found to be feature-complete based on the task list for that version
