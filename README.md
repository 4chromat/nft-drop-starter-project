### Location triggered NFTs

## To get started
1. cd into the `app` folder
2. Run `npm install` at the root of your directory
3. Run `npm run start` to start the project

## To change the NFTs:
​​1. Delete the `.cache` folder that was generated by the Metaplex CLI's candy machine commands.
2. Change up your NFT files to be whatever you want in `app/assets`.
3. Run Metaplex's upload command via the CLI to upload the NFTs and create a new candy machine.
```
ts-node ~/metaplex/js/packages/cli/src/candy-machine-v2-cli.ts verify_upload -e devnet -k ~/.config/solana/devnet.json
```
4. Run Metaplex's verify command via the CLI to make sure the NFTs were uploaded and the candy machine was properly configured.
```
ts-node ~/metaplex/js/packages/cli/src/candy-machine-v2-cli.ts verify_upload -e devnet -k ~/.config/solana/devnet.json
```
5. Update your `.env` file with the new address.  Remember to add `.env.` to `.gitignore`.

## To update collection configurations
Everytime `config.json` is changed, i.e. to update drop start date, we need to update the Candy Machine:
```
$ ts-node ~/metaplex/js/packages/cli/src/candy-machine-v2-cli.ts update_candy_machine -e devnet  -k ~/.config/solana/devnet.json -cp config.json
```

## To get free dev money:
```
$ solana balance
$ solana airdrop 2  <address>
```
## Install Solana
```
$ sh -c "$(curl -sSfL https://release.solana.com/stable/install)"
$ export PATH="/Users/cynthia/.local/share/solana/install/active_release/bin:$PATH"
```

# Install Metaplex
```
$ git clone -b v1.1.1 https://github.com/metaplex-foundation/metaplex.git ~/metaplex
$ yarn install --cwd ~/metaplex/js/
```

## Credits
Building blocks taken from Buildspace "Ship your own custom NFT collection on Solana w/ Metaplex in a weekend"
