name: Example Workflow
on:
  workflow_dispatch:
    inputs:
      my_dropdown:
        type: choice
        description: Select an option
        options:
          - option1
          - option2
          - option3
jobs:
  my_job:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v2
      - name: Run a script
        run: echo "Selected option: ${{ github.event.inputs.my_dropdown }}"
