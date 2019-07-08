#!/bin/python3
##
# Author: Bertrand Benoit <mailto:contact@bertrand-benoit.net>
# Description: Git Hook (server-side) allowing to prevent merge from some branches to anothers
## Version: 0.9
"""
Git Hook (server-side) allowing to prevent merge from some branches to anothers.

N.B.: currently it is only possible to configure one source branch, and one destination one.
The next version will allow combinations.

**FORBIDDEN_SOURCE_BRANCH** defines the SOURCE branch of a merge which must be regarded
**FORBIDDEN_IF_NOT_DEST_BRANCH** defines the DESTINATION branch which is the ONLY ONE
    allowed from the source branch
All other attempts to merge the FORBIDDEN_SOURCE_BRANCH branch in another, will failed
    with a specific message.
"""
import sys
import subprocess
import re

# Configuration begin - adapt constants to your needs.
#
FORBIDDEN_SOURCE_BRANCH = 'testing'
FORBIDDEN_IF_NOT_DEST_BRANCH = 'master'
# Configuration end.


# Considers only merge commit.
if not (len(sys.argv) >= 2 and sys.argv[2] == 'merge'):
    sys.exit(0)

# Defines which is the source branch.
with open(sys.argv[1], 'r') as f:
    mergeMessage = f.readline()
mergeBranchExtract = re.compile(
    "Merge branch '([^']*)'.*$").search(mergeMessage)
if not mergeBranchExtract:
    print('Unable to extract branch to merge from message: ', mergeMessage)
    sys.exit(0)  # Ensures normal merge as failback

# Checks if the merge (source) branch is one of those to check.
mergeBranch = mergeBranchExtract.group(1)
if mergeBranch != FORBIDDEN_SOURCE_BRANCH:
    sys.exit(0)  # It is NOT the forbidden source branch, so keeps on normal merge

# Defines which is the current branch.
currentBranchFullName = subprocess.check_output(
    ['git', 'symbolic-ref', 'HEAD'])
currentBranchExtract = re.compile(
    "^.*/([^/]*)\n$").search(currentBranchFullName)
if not currentBranchExtract:
    print('Unable to extract current branch from: ', currentBranchFullName)
    sys.exit(1)  # Ensures normal merge as failback

# Checks if the current (destination) branch is one of those to check.
currentBranch = currentBranchExtract.group(1)
if currentBranch != FORBIDDEN_IF_NOT_DEST_BRANCH:
    print(
        "FORBIDDEN: Merging from '",
        mergeBranch,
        "' to '",
        currentBranch,
        "' is NOT allowed. Contact your administrator.",
        "Now, you should use git merge --abort and keep on your work.")
    sys.exit(1)  # This is exactly the situation which is forbidden

# All is OK, so keeps on normal merge
sys.exit(0)
