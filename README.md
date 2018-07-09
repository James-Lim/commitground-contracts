# Commitground Contracts

This repository is used to develop & test the smart contracts for commitground using the truffle framework.

# Repository Structure

```.bash
.
├── .git
├── contracts
│   ├── .git
│   ...
│   └── Contracts.sol
├── build
├── migrations
│   ├── 1_initial_migration.js
│   └── 2_deploy_contracts.js
├── package.json
├── package-lock.json
├── test
│   ├── ...
│   └── testcase.js
└── truffle.js
```

- `contracts`:
  Smart contracts written in Solidity are here.

- `test`:
  This is a directory for test cases. Keep in mind that writing test cases is dependent on the *contract* submodule.

- Etc
    - `build`: Build artifacts are stored in this directory.
    - `migtrations`: Script to test or deploy the contracts

# Prerequisites

1. Install truffle

    ```.bash
    npm install -g truffle
    ```
    You can read truffle install doc [here](https://truffleframework.com/docs/getting_started/installation)

1. Ganache(One click ethereum private net).

    Two options exist. When you run this repository on your local environment, desktop app will help you know what's happening on the blockchain. But for the CI/CD environment, 'ganache-cli' will be a better option.
    - [ganache-cli](https://github.com/trufflesuite/ganache-cli)
    - [ganache desktop app](https://truffleframework.com/ganache)

# Run test

- Running test with ganache-cli.
    ```.bash
    ./run-test.sh
    ```
- Running test with ganache desktop app
    - First, launch the ganache app
    - Run the following command
        ```
        truffle test
        ```

# Contributing

1. Fork this project.

    - commitground-contracts: [![Fork](https://img.shields.io/github/forks/commitground/commitground-contracts.svg?style=social&label=Fork)](https://github.com/commitground/commitground-contracts/fork)

1. Clone your forked *commitground-contract* repository first.

    ```.bash
    $ git clone https://github.com/commitground/commitground-contracts
    ```

1. Make branches following the convention. Please check [this](https://github.com/commitground/guide)

    ```.bash
    $ git checkout -b $BRANCH_NAME #e.g. feature/create-project
    ```

1. Write test cases for a new contract. Read [this](https://truffleframework.com/docs/getting_started/javascript-tests) to know how to write a test case.

    ```.bash
    $ touch test/testCreateProject.js # write test cases here
    ```

1. Write a new contract & implement.

    ```.bash
    $ touch contracts/createProject.sol # write contracts here
    ```

1. Write a migration script. Read [this](https://truffleframework.com/docs/getting_started/migrations).

    ```.bash
    $ touch migrations/n_script_title.js # write contracts here
    ```

1. If it passes your test cases, push & make pull request.

    ```.bash
    $ ./run-test.sh
    $ git add contracts test
    $ git commit -m "Add 'createProject' contract"
    $ git push origin $BRANCH_NAME # forked repository on your github account
    ```
