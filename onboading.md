# Bunchd NFT Alpha Onboarding

We're excited to get you all setup with your own Bunchd NFT Canister. As a quick reminder, this is alpha software. We encourage you to experiment, and expect some bugs!

For the time being we have added ourselves as a controller for your canister so we can push fixes and upgrade you to the final version of the software in the future. Having controller access means we have *complete control* over the canister. For this reason, we have not built any good ways to sell Bunchd NFTs. This will be a future addition once we remove ourselves as controllers. 

## Getting Started

In order to get you online we need three pieces of information from you:

### Contract Name

Integrators might use this for display purposes in applications. This cannot be changed once set.

Examples:
- Bunchd NFTs
- The Sidewalk Project
- 🚗 and more

### Contract Symbol

Integrators might use this for display purposes in applications. This cannot be changed once set.

Examples:
- BCND
- HZLD
- TOKEN
- 🥚
- 🚀
- 🐶🐶🐶🐶🐶

### UserId

Your can get your userId after [logging in here with Internet Identity](https://xe5ii-jiaaa-aaaaf-qaaya-cai.raw.ic0.app/nft/admin). An example UserId is shown in the picture below.

![UserId in UI](https://xn6du-7aaaa-aaaaf-qaazq-cai.raw.ic0.app/image/6789C6548B52A0C86C9A5DF2BAFF1EDEBAA98CFE31703217C7A6949EA03FDDAF)

## Getting You Canister

**Once you've compiled all this information fill out [the following form](https://forms.gle/WuX7FwviMHVvw3RZ6) and we'll be in touch with your canister id!**

## FAQ

### How much data can my contract store?

1GB would be a safe answer. However, because of the way canister memory grows you should anticipate that your canister will be using 2X the actual size of the data uploaded. This is a consequence of the Motoko garbage collector. 

### What are the costs for my canister?
Every time a request is made to your canister it consumes cycles. On the Internet Computer there are two types of calls which can be made. Query calls, and Update calls. Query calls cannot mutate state, and do not require consensus. Update calls, can update state, and require consensus. Query calls are significantly cheaper than Update calls. Generally, your canister will be serving its data via query calls. However, uploading assets and minting requires Update calls. Finally, your canister consumes cycles proportional to its memory size at a rate of `0.127 cycles/s` per byte of memory.

You can calculate how many cycles your contact is consuming *per year* using the following equation:

`memory_size_bytes * 4005580`

As an example, if your canister's memory size was 2GB you would do:
`2000000 * 4005580 = ~8e12` which comes to to be about $11.52USD

**How much does it cost to serve data to the web?**

From our testing 1 Trillion cycles ($1.44USD) should be able to serve 5-10 Terabytes of data to the browser. 

So, for 1 Trillion cycles you could serve:
| Size | Lower Number of Times | Upper Number of Times
|--|--| -- |
| 1MB | 5_000_000 | 10_000_000 |
| 100KB | 50_000_000 | 100_000_000
| 10KB | 500_000_000 | 1_000_000_000 

When minting take into account how the additional data will effect your canisters life and how often you expect the image to be served. Note, canisters can be topped up with cycles at any time, by anyone. 

### What happens if my canister runs out of cycles?

The short version is it will eventually get destroyed - but don't worry every deployed canister is configured with a [freezing threshold](https://sdk.dfinity.org/docs/interface-spec/index.html#_calls_to_stoppedstoppingfrozen_canisters_are_rejected) of 1 year. The freezing threshold essentially tells this internet computer.

> Lock this canister once it's cycle balance falls below the required amount of cycles to host its data for X amount of time.

If your canister becomes frozen, it will reject all calls until its balance it topped off above the threshold. In the future Bunchd will allow users to raise this threshold.

### What rights do you have over the data in my canister?

None - your data, art, anything you upload into your canister is yours. We are maintaining controller access to your canister only for pushing bug fixes, debugging issues, and updating your canister to the final version of the software.

### How can I sell my NFTs

Short term you don't. We have controller access to your canister which you should treat as a security risk until we remove ourselves.
