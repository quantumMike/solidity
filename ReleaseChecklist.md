Checklist for making a release:

 - [ ] Check that all "nextrelaese" issues and pull requests are merged to develop
 - [ ] Create a commit in develop that updates the Changelog to include a release date (run the tests locally to update the bug list).
 - [ ] Create a pull request and wait for the tests, merge it.
 - [ ] Create a pull requets from develop to release, wait for the tests, merge it.
 - [ ] Make a final check that there are no platform-dependency issues in the solc-test-bytecode repository
 - [ ] Wait for the tests for the commit on release, create a release in Github, creating the tag.
 - [ ] Thank voluntary contributors in the github release page (use ``git shortlog -s -n -e origin/release..origin/develop``)
 - [ ] Wait for the CI runs on the tag itself (they should push artefacts onto the Github release page)
 - [ ] Run ``scripts/release_ppa.sh release`` to create the PPA release (you need the relevant openssl key)
 - [ ] Check that the docker release was pushed to docker hub (this still seems to have problems)
 - [ ] Make a release of solc-js: Increment the version number, create a pull request for that, merge it after tests succeeded
 - [ ] Run ``npm publish`` in the solc-js updated repository.
 - [ ] Create a commit to increase the version number on develop in CMakeLists.txt and add a new skeleton changelog entry.
 - [ ] Merge release back into develop.
 - [ ] Announce on twitter and reddit.
