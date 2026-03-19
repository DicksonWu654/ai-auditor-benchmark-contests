# Official High and Medium Findings

| Finding ID | Severity | Title | Description |
| --- | --- | --- | --- |
| H-01 | High | Signature replay in signatureClaim results in unauthorized claiming of rewards | A signature intended for one chain can be reused elsewhere, allowing unauthorized and repeated reward claims. |
| H-02 | High | Signature replay in createArt allows to impersonate artist and steal royalties | The createArt signature is not sufficiently bound to the original artist context, so an attacker can reuse it to impersonate the artist and redirect royalties. |
| H-03 | High | shareBalance bloating eventually blocks curator rewards distribution | Zero-balance share entries accumulate in storage until rewards distribution can no longer iterate the curator set reliably. |
| H-04 | High | Forced endTime extension in updateArtSettings() allows attacker to mint more tokens | An art creator can extend the mint window after the fact, reopening minting and enabling extra token issuance. |
| H-05 | High | Exposed _removeCredIdPerAddress & _addCredIdPerAddress allows anyone to cause issues to current holders as well as upcoming ones | The exposed address-to-cred bookkeeping lets an attacker alter holder state and break intended claim / ownership behavior. |
| H-06 | High | Reentrancy in creating Creds allows an attacker to steal all Ether from the Cred contract | Reentrancy during Cred creation lets an attacker reenter before state is finalized and drain Ether from the contract. |
| H-07 | High | Unrestricted changes to token settings allow artists to alter critical features | Artists can change URI, royalty, and soulbound settings after minting, which can alter transferability, fees, and metadata for existing holders. |
| M-01 | Medium | Contract PhiNFT1155 can’t be paused | The pause mechanism is ineffective, so NFTs remain transferable even when the contract is paused. |
| M-02 | Medium | Incorrect fee handling prevents protocol from updating fees | The fee update logic uses incorrect checks, which prevents the protocol from reliably changing its configured fees. |
| M-03 | Medium | PhiFactory:claim potentially causing loss of funds if mintFee changed beforehand | Claim execution recomputes the mint fee at call time, so a fee change between quote and claim can lead to incorrect payment handling and fund loss. |
| M-04 | Medium | Cred creator could cause stuck funds | A creator can raise share-sale royalties after issuance, making selling uneconomic and potentially trapping user funds. |
| M-05 | Medium | Lack of data validation when users are claiming their art allows malicious user to bypass signature/merkle hash to provide unapproved ref_ , artId_ and imageURI | Claim data is not fully bound into the approval hash, allowing a claimer to substitute unapproved values such as `ref_`, `artId_`, and `imageURI`. |
| M-06 | Medium | PhiNFT1155 contracts continue sending fees/royalties to old protocol destination address | Existing NFT contracts cache the old fee destination, so updating the factory destination does not redirect fees on already deployed instances. |
| M-07 | Medium | Attacker can DOS user from selling shares of a credId | An attacker can keep buying tiny amounts of shares for a curator and force repeated lock periods, delaying or blocking sales. |
| M-08 | Medium | Refunds sent to incorrect addresses in certain cases | Refund logic can send ETH to `_msgSender()` instead of the original payer in some flows, causing refunds to land at the wrong address. |
