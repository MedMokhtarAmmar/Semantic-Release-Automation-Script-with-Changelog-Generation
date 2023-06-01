# Script: semantic-release.sh

This script automates the process of semantic versioning and generating release notes for Git repositories. It follows conventional commit message standards to determine the version increment (major, minor, or patch) and creates a new tag for the release. It also generates a changelog based on the commit messages since the last release.

## Prerequisites

The following tools are required for the script to work properly:

- awk
- basename
- cat
- curl
- jq
- git
- touch

Make sure these tools are installed and accessible in your system's PATH.

## Configuration

Before using the script, you need to configure the following variables:

- `RELEASE_BRANCH`: The branch to use for creating releases (default: "master").
- `REGEX_CONVENTIONAL_COMMITS`: Regular expression pattern for conventional commit messages. Only commits matching this pattern will be considered for versioning.
- `REGEX_MAJOR`: Regular expression pattern indicating a breaking change.
- `REGEX_MINOR`: Regular expression pattern indicating a new feature.
- `REGEX_PATCH`: Regular expression pattern indicating a bug fix.

## Authentication

The script requires a GitHub personal access token (`GH_TOKEN`) with the necessary permissions to create releases and tags. Set the `GH_TOKEN` environment variable before running the script.

## Usage

To use the script, simply run it in a Git repository:

```shell
./semantic-release.sh
