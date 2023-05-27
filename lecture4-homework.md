# 第 4 课 练习

Check out https://semaphore.appliedzkp.org/ and set up a starter project!

## Usage

### Compile contracts

```shell
> npm run compile

> monorepo-ethers-contracts@1.0.0 compile
> hardhat compile

√ Help us improve Hardhat with anonymous crash reports & basic usage data? (Y/n) · y
Downloading compiler 0.8.4
Generating typings for: 12 artifacts in dir: ./build/typechain for target: ethers-v5
Successfully generated 40 typings!
Compiled 14 Solidity files successfully
```

### Test contracts

#### npm test

```shell
> monorepo-ethers-contracts@1.0.0 test
> hardhat run scripts/download-snark-artifacts.ts && hardhat test



  Feedback
    # joinGroup
      √ Should allow users to join the group (1158ms)
    # sendFeedback
      √ Should allow users to send feedback anonymously (3327ms)


  2 passing (8s)
```

#### npm run test:coverage

```shell
> monorepo-ethers-contracts@1.0.0 test:coverage
> hardhat coverage


Version
=======
> solidity-coverage: v0.7.22

Instrumenting for coverage...
=============================

> Feedback.sol

Compilation:
============

Generating typings for: 12 artifacts in dir: ./build/typechain for target: ethers-v5
Successfully generated 40 typings!
Compiled 14 Solidity files successfully

Network Info
============
> HardhatEVM: v2.14.0
> network:    hardhat



  Feedback
    # joinGroup
      √ Should allow users to join the group (1298ms)
    # sendFeedback
      √ Should allow users to send feedback anonymously (3399ms)


  2 passing (8s)

---------------|----------|----------|----------|----------|----------------|
File           |  % Stmts | % Branch |  % Funcs |  % Lines |Uncovered Lines |
---------------|----------|----------|----------|----------|----------------|
 contracts\    |      100 |      100 |      100 |      100 |                |
  Feedback.sol |      100 |      100 |      100 |      100 |                |
---------------|----------|----------|----------|----------|----------------|
All files      |      100 |      100 |      100 |      100 |                |
---------------|----------|----------|----------|----------|----------------|

> Istanbul reports written to ./coverage/ and ./coverage.json
```

#### npm run test:report-gas

```
> monorepo-ethers-contracts@1.0.0 test:report-gas
> REPORT_GAS=true hardhat test

Compiled 14 Solidity files successfully

  Feedback
    # joinGroup
      ✓ Should allow users to join the group
    # sendFeedback
      ✓ Should allow users to send feedback anonymously

·-----------------------------|----------------------------|-------------|-----------------------------·
|     Solc version: 0.8.4     ·  Optimizer enabled: false  ·  Runs: 200  ·  Block limit: 30000000 gas  │
······························|····························|·············|······························
|  Methods                                                                                             │
·············|················|·············|··············|·············|···············|··············
|  Contract  ·  Method        ·  Min        ·  Max         ·  Avg        ·  # calls      ·  usd (avg)  │
·············|················|·············|··············|·············|···············|··············
|  Feedback  ·  joinGroup     ·     896154  ·     1656004  ·    1276079  ·            4  ·          -  │
·············|················|·············|··············|·············|···············|··············
|  Feedback  ·  sendFeedback  ·          -  ·           -  ·     396055  ·            2  ·          -  │
·············|················|·············|··············|·············|···············|··············
|  Deployments                ·                                          ·  % of limit   ·             │
······························|·············|··············|·············|···············|··············
|  Feedback                   ·          -  ·           -  ·    1514107  ·          5 %  ·          -  │
······························|·············|··············|·············|···············|··············
|  IncrementalBinaryTree      ·          -  ·           -  ·    1667044  ·        5.6 %  ·          -  │
······························|·············|··············|·············|···············|··············
|  Pairing                    ·          -  ·           -  ·    1204971  ·          4 %  ·          -  │
······························|·············|··············|·············|···············|··············
|  Semaphore                  ·          -  ·           -  ·    1846388  ·        6.2 %  ·          -  │
······························|·············|··············|·············|···············|··············
|  SemaphoreVerifier          ·          -  ·           -  ·    7357877  ·       24.5 %  ·          -  │
·-----------------------------|-------------|--------------|-------------|---------------|-------------·

  2 passing (5s)
```

