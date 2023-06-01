Script: semantic-release.sh
This script automates the process of semantic versioning and generating release notes for Git repositories. It follows conventional commit message standards to determine the version increment (major, minor, or patch) and creates a new tag for the release. It also generates a changelog based on the commit messages since the last release.

Prerequisites
The following tools are required for the script to work properly:

awk
basename
cat
curl
jq
git
touch
Make sure these tools are installed and accessible in your system's PATH.

Configuration
Before using the script, you need to configure the following variables:

RELEASE_BRANCH: The branch to use for creating releases (default: "master").
REGEX_CONVENTIONAL_COMMITS: Regular expression pattern for conventional commit messages. Only commits matching this pattern will be considered for versioning.
REGEX_MAJOR: Regular expression pattern indicating a breaking change.
REGEX_MINOR: Regular expression pattern indicating a new feature.
REGEX_PATCH: Regular expression pattern indicating a bug fix.
Authentication
The script requires a GitHub personal access token (GH_TOKEN) with the necessary permissions to create releases and tags. Set the GH_TOKEN environment variable before running the script.

Usage
To use the script, simply run it in a Git repository:

shell
Copy code
./semantic-release.sh
The script will perform the following steps:

Check the prerequisites and repository requirements.
Determine the latest tag and calculate the next version based on commit messages.
Generate a changelog with the commit messages since the last release.
Create or update the CHANGELOG.md file.
Commit the changes and push them to the repository.
Create a new tag for the release and push it to the repository.
Create a new GitHub release with the changelog as the release body.
Notes
The script assumes the repository uses the GitHub remote URL for the origin.
The script requires internet access to interact with GitHub's API.
If no previous semVer releases are found, the script will start from version 1.0.0.
The script automatically detects if the current branch is different from the release branch and marks the release as a pre-release if they differ.
Feel free to customize the script according to your specific needs or requirements.
