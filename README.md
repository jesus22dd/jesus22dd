name: generate snake
on:
  schedule:
    - cron: "0 12 * * *"
  workflow_dispatch:
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: Platane/snk@v3
        with:
          github_user: jesus22dd
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
