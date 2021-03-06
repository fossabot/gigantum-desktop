## 2018-09-06

### Gigantum Client (0.10.0)

Image Tag: 36e27262 (243665950)

Image ID: ace6c07d0b0b

* New
	* Added ability to publish both public and private projects

* Improved
  * Import projects now show build progress
  * Base images updated to latest package versions
  * Added additional error handling during environment component checkout

* Fixed
  * Membership is now properly enforced when listing cloud projects
  * Fixed bug with using Gigantum Client offline when starting cold without an internet connection
  * Added retry on remote project creation during publish
  * Fixed issues related to latest package version lookups
  * Sync and publish are now properly locked during export
  * Readme editing is now properly locked during sync and publish

* Known Issues
  * Container builds with conda packages are not yet optimized and can be slow
  * Maximum size of an individual file upload is currently limited to 1.8GB


### Gigantum Desktop App (0.5.4)

* New
  * Updated Gigantum Client container to latest release 0.10.0

* Fixed
  * Fixed issue with container naming convention
  * Fixed issue with docker being reported as not running when the Gigantum Client container fails to start


## 2018-08-10

### Gigantum Client (0.9.4)

Image Tag: 75efef53 (244853862)

Image ID: ba10850e1beb

* New
	* Added notification tray that provides a better display of messages along with the ability to see previous messages
	* Added the ability to view build output from Docker in the notification tray
	* Added additional hashing of the environment configuration to avoid unnecessary container re-builds on things like sync and checkout
	* Added link to feedback form accessible from help menu

* Improved
  * Improved utiliziation of the Docker build cache by adjusting the order of some build instructions added to containers by the Gigantum Client
  * Authentication token refresh now happens automatically in the background, reducing the number of times a user needs to log in to access cloud resources
  * Improved API down page text and help documentation

* Fixed
  * Fixed bug in Project sorting that resulted in wrong sort order
  * Fixed bug that prevented the correct environment configuration from being displayed in the UI after switching branches
  * Starting a container while editing the environment is now properly blocked during package validation
  * Fixed bug that was causing any uploaded zip file to trigger an import

* Known Issues
  * Container builds with conda packages are not yet optimized and can be slow
  * Maximum size of an individual file upload is currently limited to 1.8GB


### Gigantum Desktop App (0.5.3)

* New
  * Updated Gigantum Client container to latest release 0.9.4

* Improved
  * Clarified version information in About window

## 2018-07-27

### Gigantum Client (0.9.3)

Image Tag: 8bcd4c2f (245020714)

Image ID: ae1d455bb34e

* Improved
  - Auto-commit skipped on Jupyter Save Hook when any kernels related to the Project are still busy. This eliminates excessive versioning during long-running cells that write data to disk.
  - Added styling to Dockerfile snippet rendering

* Fixed
  - Fixed latest version lookups for package managers to complete more efficiently and not block builds. This was particularly an issue when using conda.
  - Fix bug that resulted in Activity Records being set to "Project" type instead of a more specific type (e.g. Code, Input Data)
  - When deleting a remote Project, it is removed from the list without needing a refresh

* Known Issues
  - Maximum size of an individual file upload is currently limited to 1.8GB


### Gigantum Desktop App (0.5.2)

* New
  - Updated Gigantum Client container to latest release 0.9.3


## 2018-07-20

### Gigantum Client (0.9.2)

Image Tag: 9ad016cd (244522922)

Image ID: 3f7dd645acac

* Added


* Improved
  - Updated Base selection UI and detail view

* Fixed
  - Fixed bug that was silently blocking container build when installing conda packages due to a race condition with latest version lookups
  - Fixed bug that sometimes made drag-and-drop to import a project fail to start uploading, requiring multiple attempts to drag-and-drop
  - Fixed bug that caused the add package widget to get stuck in an unusable state if you added a single package twice in a row

* Known Issues
  - Maximum size of an individual file upload is currently limited to 1.8GB


### Gigantum Desktop App (0.5.1)

* New
  - Updated Gigantum Client container to latest release 0.9.2


# 2018-07-16

### Gigantum Client (0.9.1)

Image Tag: 6f19937d (246462735)

Image ID: 486bb97862d2

* Added
  - Help interface, providing quick access to docs, help, and guide
  - Added real-time metadata to background jobs (improved UI in next release)
  - LabBooks have been renamed to Projects
  - Added latest version lookup and interface to update packages

* Improved
  - During file uploads, directories are automatically created without additional API calls, boosting upload performance
  - .lbk files are now .zip to make it more clear they are simply archives
  - User identity retrieval and local caching for offline use now done with JWTs

* Fixed
  - File based import/export uses improved archive method to fix issues seen when moving between windows and mac/linux
  - Fixed issue that limited the cloud view from listing more than 20 projects
  - Fixed bug that caused slow responses and high CPU when listing lots of files in the file brower widgets
  - Fixed issues related to container build status UI
  - Fixed additional minor bugs and UI clean up

* Known Issues
  - Maximum size of an individual file upload is currently limited to 1.8GB


### Gigantum Desktop App (0.5.0)

* New
  - Updated Gigantum Client container to latest release 0.9.1
  - Added crash reporting

* Fixed
  - Gigantum Desktop no longer blocks restart on macOS
  - Bind mount mode is set to cached only on macOS


## 2018-06-27

### Gigantum Client (0.9.0)

Image Tag: df4dbd9a (268290698)

Image ID: 4a55a8dcedc8

* Added
  - All traffic now runs behind an HTTP proxy, allowing the application and all jupyter servers to run on a single port

* Improved
  - Package manager add and remove operations are now batched into a single Activity Record
  - Package manager version lookups are now batched
  - Improved the LabBook listing filter and search UI

* Fixed
  - Fixed a session caching bug, which caused an error on load if token has expired
  - Added a temporary patch for running JupyterLab in python2
  - Fixed bug so containers are re-built on rollback
  - Minor bugs and UI clean up

* Known Issues
  - "Latest Version" lookup for packages has been temporarily removed from the "Environment" tab
  - Maximum size of an individual file upload is currently limited to 1.8GB


### Gigantum Desktop App (0.4.0)

* New
  - Updated Gigantum Client container to latest release 0.9.0

* Fixed
  - Gigantum Desktop no longer blocks a restart on macOS


## 2018-06-12

### Gigantum Client (0.8.2)

Image Tag: 779847b0 (209566418)

Image ID: 7582a9bfc1f5

* Added
  - Initial support for R in JupyterLab

* Improved
  - Updated file uploads to "batch" into a single activity record
  - Updated date widget to stick to the top of the activity feed
  - Updated Activity bundling interface
  - Updated LabBook submenu to be visible when scrolling through activity feed
  - Updated LabBook listing page to load progressively
  - Reorganized filters and added search to LabBook listing page

* Fixed
  - Minor bugs and UI clean up
  - When deleting a Cloud LabBook that still exists locally, the git configuration is now updated so you can re-publish without error
  - An error during publish no longer breaks future LabBook syncs

* Known Issues
  - "Latest Version" lookup for packages has been temporarily removed from the "Environment" tab
  - Adding Conda packages is very slow


### Gigantum Desktop App (0.3.0)

* New
  - Updated Gigantum Client container to latest release 0.8.2


## 2018-05-25

### Gigantum Client (0.8.1)

Image Tag: 4388c439 (212025636)

Image ID: 6d3b8809246e

* Added
  - Rollback capability for the primary workspace branch from within the Activity Feed
  - Activity record generation when a LabBook container is stopped
  - Activity record generation when a Jupyter notebook is saved
  - Activity record generation when files are swept up and committed during certain internal operations (e.g. pre-publish, switch branch, etc.)
  - "Action" modifiers on Activity records to better sort activity and improve UI/UX

* Improved
  - Activity feed UI
  - Activity feed now properly hides minor detail records
  - Activity feed now bundles 3+ minor activity records together to reduce clutter
  - Updated application containers to Ubuntu 18.04
  - Updated LabBook containers to Ubuntu 18.04
  - Custom Docker instructions now execute after all packages are installed
  - Added placeholder for LabBooks while loading

* Fixed
  - Minor bugs and UI clean up
  - Description is now properly set when creating a new branch
  - Selecting "Switch Branch" from the action menu scrolls to the top
  - LabBook tab menu doesn't flip out when you mouse over the wrong spot

* Known Issues
  - "Latest Version" lookup for packages has been temporarily removed from the "Environment" tab
  - Adding Conda packages is very slow


### Gigantum Desktop App (0.2.0)

* New
  - Updated Gigantum Client container to latest release 0.8.1

* Fixed
  - Minor UI bugs
  - Issues related to updates when disconnected from the internet


## 2018-05-16

### Gigantum Client (0.8.0)

Image Tag: 9de7af05 (459914384)

Image ID: 63f300779787

* Added
  - Readme to the Overview section
  - Ability to add a custom Docker snippet to a LabBook container build
  - New "Cloud" view to the LabBook listing screen, including the ability to import and delete LabBooks stored in the Gigantum Cloud
  - Collaborator usernames auto-complete while typing
  - Automatic `git gc` operations to reduce git repository size

* Improved
  - Package validation and version lookup now occurs in target LabBook container. Future additions will improve package lookup speed.
  - Improved import/publish/sync speed when there are lots of files in input and output sections of a LabBook
  - Activity feed now only loads data if being actively viewed, reducing load on the client and browser when working for a long time in Jupyter
  - Disconnect screen shows different instructions for Mac, Windows, and Linux
  - Share URLs updated to route through gigantum.com

* Fixed
  - Force merge dialog boxes now actually force merge
  - Favorite cards no longer stack incorrectly when resizing a page
  - 12pm is no longer displayed as 12am in the activity feed
  - Lots of minor bugs and UI clean up

* Known Issue
  - "Latest Version" lookup for packages has been temporarily removed from the "Environment" tab
  - Adding Conda packages is very slow


### Gigantum Desktop App (0.1.0)

* New
  - Initial Release 🎉
