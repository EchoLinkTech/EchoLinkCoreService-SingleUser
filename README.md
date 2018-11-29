# Single-user
Dapp to add and query user info, job and experiences on parity node.

## Prerequisites

- Private account:
User should have a private account with mnemonic key to start a transaction. If he don't have mnemonic key, single-user Dapp gives you an option to create a new account via its interface. After successful account creation, user will be provided with a mnemonic which can be downloaded and saved securely.

- Mnemonic key
After click on metamask logo, you will be provided with an option to `Create a new vault`. Enter a strong password and click `OK`. Metamask will now show you your seed(mnemonic key). It is very important that you copy and store those 12 words, without them you cannot restore your wallet. 

## Steps to run single-user on local system

- Clone the repo `EchoLinkPrivateService`

- Go to credentials-bulk-upload module and run `npm install`

- Start the server: 
`npm start`

- UI can be accessed on [localhost:3000](http://localhost:3000).
- The server is deployed and can be accessed on [http://18.216.156.198:3000/](http://18.216.156.198:3000/)

On start, a dialog will appear which will ask user to `Enter Mnemonic key`.
After entering the valid mnemonic key, you can see the dashboard containing your acccount address and balance on top right corner.

If you don't have metamask account, you can create a new account by clicking `Create New Account`. On clicking, you'll get a new mnemonic which can be copied somewhere or downloaded. After that, click `I've saved my mnemonic somewhere` and enter the new mnemonic in the textbox.
After key validation, you can see the dashboard and perform transactions.

You can perform the following transactions:

#### Submit Credentials
User need to enter following details

- issuer 
- recipient
- status
- image
    
User can save the credentials to blockchain using `Save` button. A `Save Credential` transaction will be executed which consumes some of your ether balance. It interacts with EKO-Pops through `CredentialStore` contarct.

#### Query Credentials
You can query the credentials in blockhain using `Status` field. It will display a list of all the matching credentials along with uploaded images. It interacts with EKO-Pops through `CredentialStore` contract.

#### Submit Posting
A user can perform a transaction to post a job (for eg, Java, SQL, Node) to EKO-Pops node. Account ether balance on parity node must be greater than `amountOfEnergyForPosting` to perform a successful transaction. It interacts with EKO-Pops through `PostingStore` contract.

#### Query Posting
Posted jobs can be queried (like Java, SQL, Node) in EKO-Pops blockchain, provided the Ether Balance is greater than  `amountOfEnergyForQuerying`. It interacts with EKO-Pops through `PostingStore` contract.

#### Add Experience
A user can add experience in some technology with years of experience and Employee Address. Account ether balance on parity node must be greater than `amountOfEnergyForPosting` to perform a successful transaction. It interacts with EKO-Pops through `ExperienceStore` contract.

#### Query Experience
Employee experience can be queried using years of experience and specific technology in EKO-Pops node provided the Ether Balance is greater than `amountOfEnergyForQuerying`. It interacts with EKO-Pops through `ExperienceStore` contract.

The transactionHash for the last successful transaction will be displayed.

#### URL to extract employers credential info
An employer can see his credential info by adding path to URL `/credential/:credentialId`. It will fetch and display the credentialData for the corresponding credentialId.
