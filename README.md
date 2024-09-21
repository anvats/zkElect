# ⚡️zkElect: Redefining Elections & Surveys with Blockchain and Zero-Knowledge Proofs

Imagine a world where every vote and survey is fully anonymous, immune to corruption, and tamper-proof. Many countries still struggle with election integrity, spending millions to ensure fairness, yet votes can still be influenced by bribery 💸 or manipulated by powerful individuals. Citizens are left with compromised elections, especially in parliamentary votes where democracy is undermined.

In workplaces, employees hesitate to provide honest feedback when they fear management might trace their responses. Similarly, companies face challenges gathering true customer insights when anonymity isn’t guaranteed, resulting in incomplete feedback.

Enter **zkElect** 🚀—the game-changing platform that transforms how elections and surveys are conducted and built on blockchain, zk-SNARKs, and MACI, zkElect guarantees complete privacy 🔒 and transparency. Every vote is cast on-chain, securely encrypted, and remains anonymous, eliminating any potential for coercion or vote-buying.

## # Why zkElect❓

**Integrity First:** Every vote is transparent, secure, and immutable on the blockchain.  
**Efficiency Boost:** Say goodbye to costly, resource-heavy elections! zkElect saves time, money, and effort by moving the process on-chain.  
**Ultimate Anonymity:** Voters' identities are protected with zk-SNARKs, preventing bribery and ensuring fear-free voting 🗳️.  
**Shield Against Pressure:** zkElect protects citizens from powerful actors, preserving democratic integrity 🌍.  
**Global Reach:** Whether it's a country, company, or community, zkElect enhances voting and feedback processes worldwide 🌐.

## ✅Requirements

Ensure you have the following tools installed before you proceed:

- [Node (>= v18.17)](https://nodejs.org/en/download/)
- Yarn ([v1](https://classic.yarnpkg.com/en/docs/install/) or [v2+](https://yarnpkg.com/getting-started/install))
- [Git](https://git-scm.com/downloads)

## 🏁Quickstart

Jumpstart your development with these simple steps:

1. **Clone and Set Up the Project**

```bash
git clone https://github.com/yashgo0018/maci-wrapper.git
cd maci-wrapper
yarn install
```

2. **Download the zkeys for the maci circuits**

In your first terminal window, run:

```bash
yarn download-zkeys
```

3. **Update the environment variables**

Copy the env example files to env files

```bash
cp packages/hardhat/.env.example packages/hardhat/.env
cp packages/nextjs/.env.example packages/nextjs/.env.local
```

Update the values of the env variables in these new .env files

4. **Start a Local Ethereum Network**

In your first terminal window, run:

```bash
yarn chain
```

This initiates a local Ethereum network via Hardhat for development and testing purposes. Adjust the network settings in `hardhat.config.ts` as needed.

5. **Deploy Contracts**

In a second terminal, deploy your test contract with:

```bash
yarn deploy
```

Find the contract in `packages/hardhat/contracts`. This script deploys your contract to the local network, with customization available in `packages/hardhat/deploy`.

6. **Launch the NextJS Application**

In a third terminal, start the NextJS frontend:

```bash
yarn start
```

7. **Compute Results**

- In a fourth terminal, clone the maci repo - `git clone git@github.com:privacy-scaling-explorations/maci.git` 
- Copy the zkeys generated from the maci wrapper repo to the cli directory of the maci repo using `cp -r maci-wrapper/packages/hardhat/zkeys maci/packages/cli`. 
- Install the dependencies using `pnpm i` and build the maci project using `pnpm run build`
- Copy the new contract addresses from the maci wrapper repo to the maci repo using `cp -r maci-wrapper/packages/hardhat/contractAddresses.json maci/packages/cli/build/contractAddresses.json`.  You can also copy the `deployed-contracts.json`file from the maci wrapper repo to the maci repo `cp maci-wrapper/packages/hardhat/deployed-contracts.json maci/packages/contracts/deployed-contracts.json`. 
- Inside the MACI repo folder, run `cp packages/contracts/deploy-config-example.json packages/contracts/deploy-config.json`
- After this you should be able to run the commands written in the [maci documentation](https://maci.pse.dev/docs/quick-start/poll-finalization).
- First merge signups, then merge messages, and then generate proof, and upload the tally.json file which is generated in the process to the admin panel after the poll is over.

Navigate to `http://localhost:3000` to interact with your dApp. Modify your app configuration in `packages/nextjs/scaffold.config.ts` and `packages/hardhat/constants.ts` as necessary.

The deployed contracts will be saved to the file `packages/hardhat/contractAddresses.json`, this file is compatible with maci cli.

The coordinator keys will be stored in the file `packages/hardhat/coordinatorKeyPair.json`.

## 🚀Usage

After setting up the project, you can:

- **Register**: Use the app's interface to register with the MACI contract and gain voting rights.
- **Create Polls & Surveys**: As an admin, you can create polls with custom questions and options.
- **Vote**: Registered voters can participate in polls, utilizing MACI's secure voting mechanism.
- **View Results**: Access poll outcomes after the voting phase ends.
- **Admin Dashboard**: Monitor and manage ongoing polls, including viewing detailed poll status.

## 🔗Deployed on-chain addresses of zkElect
        Verifier: 0xB1abb44291ff487f96636758b07Ccd9881f64c9A
        PoseidonT3: 0x07490eba00dc4ACA6721D052Fa4C5002Aa077233
        PoseidonT4: 0xbb0e724CE02e5E7eDd31e632dc6e59F229a1126d
        PoseidonT5: 0xE0398F7DFAC494c530F6404AfEaC8669ABeD2679
        PoseidonT6: 0xfD77833F10a29c76A6a0ede235Eb651D744d0E2F
        PollFactory: 0xad844a9567ada5996FFC0D2DeC78b3767a1c0501
        MessageProcessorFactory: 0xbBb6f1B4232F993e5a026217a3D596B332062CB3
        TallyFactory: 0x1356f05179cdcAD2D8708B539A75de082118de92
        VkRegistry: 0x42B1AB3d98B8235204E75112e5d9E974cE7531cC
        ConstantInitialVoiceCreditProxy: 0x6f9F7Fef2FF7F5D1Ff8966F751EC154146d8f431
        FreeForAllGatekeeper: 0x6b414ff158581Ac940797463a44221d0ba6A0B9C
        MACI: 0xB78834bfEF9D0AE398e14443853ABE5729528735
        Poll-poll-0: 0x66e0684E536445E3724ee377Cabb1EF00cf1896A
