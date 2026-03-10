name: Verify Human Identity

on:
  workflow_dispatch:

jobs:
  verify:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repo
        uses: actions/checkout@v3

      - name: Install ClawHub skill
        run: npx clawhub@latest install verified-agent-identity

      - name: Link Human to Agent
        run: npx clawhub@latest verified-agent-identity link --name "benyindra" --description "benyindra AI Agent"