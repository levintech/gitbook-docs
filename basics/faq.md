# FAQ

## Why do we need BigHeadDAO in the first place?

Dollar-pegged stablecoins have become an essential part of crypto due to their lack of volatility as compared to tokens such as Bitcoin and Ether. Users are comfortable with transacting using stablecoins knowing that they hold the same amount of purchasing power today vs. tomorrow. But this is a fallacy. The dollar is controlled by the US government and the Federal Reserve. This means a depreciation of dollar also means a depreciation of these stablecoins.

BigHeadDAO aims to solve this by creating a free-floating reserve currency, BHD, that is backed by a basket of assets. By focusing on supply growth rather than price appreciation, BigHeadDAO hopes that BHD can function as a currency that is able to hold its purchasing power regardless of market volatility.

## Is BHD a stable coin?

No, BHD is not a stable coin. Rather, BHD aspires to become an algorithmic reserve currency backed by other decentralized assets. Similar to the idea of the gold standard, BHD provides free floating value its users can always fall back on, simply because of the fractional treasury reserves BHD draws its intrinsic value from.

## BHD is backed, not pegged.

Each BHD is backed by 1 DAI, not pegged to it. Because the treasury backs every BHD with at least 1 DAI, the protocol would buy back and burn BHD when it trades below 1 DAI. This has the effect of pushing BHD price back up to 1 DAI. BHD could always trade above 1 DAI because there is no upper limit imposed by the protocol. Think pegged == 1, while backed >= 1.

You might say that the BHD floor price or intrinsic value is 1 DAI. We believe that the actual price will always be 1 DAI + premium, but in the end that is up to the market to decide.

## How does it work?

At a high level, BigHeadDAO consists of its protocol managed treasury, protocol owned liquidity ([POL](broken-reference)), bond mechanism, and staking rewards that are designed to control supply expansion.

Bond sales generate profit for the protocol, and the treasury uses the profit to mint BHD and distribute them to stakers. With [liquidity bonds](broken-reference), the protocol is able to accumulate its own liquidity. Check out the entry below on [the importance of POL](faq.md#why-is-pol-important).

## What is the deal with (3,3) and (1,1)?

(3,3) is the idea that, if everyone cooperated in BigHead, it would generate the greatest gain for everyone (from a [game theory](https://en.wikipedia.org/wiki/Game\_theory) standpoint). Currently, there are three actions a user can take:

* Staking (+2)
* Bonding (+1)
* Selling (-2)

Staking and bonding are considered beneficial to the protocol, while selling is considered detrimental. Staking and selling will also cause a price move, while bonding does not (we consider buying BHD from the market as a prerequisite of staking, thus causing a price move). If both actions are beneficial, the actor who moves price also gets half of the benefit (+1). If both actions are contradictory, the bad actor who moves price gets half of the benefit (+1), while the good actor who moves price gets half of the downside (-1). If both actions are detrimental, which implies both actors are selling, they both get half of the downside (-1).

Thus, given two actors, all scenarios of what they could do and the effect on the protocol are shown here:

![](../.gitbook/assets/game\_theory.png)

* If we both stake (3, 3), it is the best thing for both of us and the protocol (3 + 3 = 6).
* If one of us stakes and the other one bonds, it is also great because staking takes BHD off the market and put it into the protocol, while bonding provides liquidity and DAI for the treasury (3 + 1 = 4).
* When one of us sells, it diminishes effort of the other one who stakes or bonds (1 - 1 = 0).
* When we both sell, it creates the worst outcome for both of us and the protocol (-3 - 3 = -6).

## Why is PCV important?

As the protocol controls the funds in its treasury, BHD can only be minted or burned by the protocol. This also guarantees that the protocol can always back 1 BHD with 1 DAI. You can easily define the risk of your investment because you can be confident that the protocol will indefinitely buy BHD below 1 DAI with the treasury assets until no one is left to sell. You can't trust the FED but you can trust the code.

As the protocol accumulates more PCV, more runway is guaranteed for the stakers. This means the stakers can be confident that the current staking APY can be sustained for a longer term because more funds are available in the treasury.

## Why is POL important?

BigHead [owns most of its liquidity](https://dune.xyz/shadow/Olympus-\(OHM\)) thanks to its bond mechanism. This has several benefits:

*   BigHead does not have to pay out high farming rewards to incentivize liquidity

    providers a.k.a renting liquidity.
*   BigHead guarantees the market that the liquidity is always there to facilitate

    sell or buy transaction.
*   By being the largest LP (liquidity provider), it earns most of the LP fees which

    represents another source of income to the treasury.
*   All POL can be used to back BHD. The LP tokens are marked down to their risk-free

    value for this purpose. You can read more about the rationale behind this in this

## Why is the market price of BHD so volatile?

It is extremely important to understand how early in development the BigHeadDAO protocol is. A large amount of discussion has centered around the current price and expected a stable value moving forward. The reality is that these characteristics are not yet determined. The network is currently tuned for expansion of BHD supply, which when paired with the staking, bonding, and yield mechanics of BigHeadDAO, result in a fair amount of volatility.

BHD could trade at a very high price because the market is ready to pay a hefty premium to capture a percentage of the current market capitalization. However, the price of BHD could also drop to a large degree if the market sentiment turns bearish. We would expect significant price volatility during our growth phase so please **do your own research** whether this project suits your goals.

## What is the point of buying it now when BHD trades at a very high premium?

When you buy and stake BHD, you capture a percentage of the supply (market cap) which will remain close to a constant. This is because your staked BHD balance also increases along with the circulating supply. The implication is that if you buy BHD when the market cap is low, you would be capturing a larger percentage of the market cap.

## What is a rebase?

Rebase is a mechanism by which your staked BHD balance increases automatically. When new BHD are minted by the protocol, a large portion of it goes to the stakers. Because stakers only see staked BHD balance instead of BHD, the protocol utilizes the rebase mechanism to increase the staked BHD balance so that 1 staked BHD is always redeemable for 1 BHD.

## What is reward yield?

Reward yield is the percentage by which your staked BHD balance increases on the next epoch. It is also known as _rebase rate_.

## What is APY?

APY stands for annual percentage yield. It measures the real rate of return on your principal by taking into account the effect of compounding interest. In the case of BigHeadDAO, your staked BHD represents your principal, and the compound interest is added periodically on every epoch (9600 BSC blocks, or around 8 hours) thanks to the rebase mechanism.

One interesting fact about APY is that your balance will grow not linearly but exponentially over time! Assuming a daily compound interest of 2%, if you start with a balance of 1 BHD on day 1, after a year, your balance will grow to about 1377. That is a lot!

![](../.gitbook/assets/apy.png)

## How is the APY calculated?

The APY is calculated from the reward yield (a.k.a rebase rate) using the following equation:

$$
APY = (1 + rewardYield)^{1095}
$$

It raises to the power of 1095 because a rebase happens 3 times daily. Consider there are 365 days in a year, this would give a rebase frequency of 365 \* 3 = 1095.

Reward yield is determined by the following equation:

$$
rewardYield = BHD_{distributed}/BHD_{totalStaked}
$$

The number of BHD distributed to the staking contract is calculated from BHD total supply using the following equation:

$$
BHD_{distibuted} = HD_{totalSupply}  * rewqrdRate
$$

Note that the reward rate is subject to change by the protocol.

## Why does the price of BHD become irrelevant in long term?

As illustrated above, your BHD balance will grow exponentially over time thanks to the power of compounding. Let's say you buy an BHD for $400 now and the market decides that in 1 year time, the intrinsic value of BHD will be $2. Assuming a daily compound interest rate of 2%, your balance would grow to about 1377 BHDs by the end of the year, which is worth around $2754. That is a cool $2354 profit! By now, you should understand that you are paying a premium for BHD now in exchange for a long-term benefit. Thus, you should have a long time horizon to allow your BHD balance to grow exponentially and make this a worthwhile investment.

## What will be BHD's intrinsic value in the future?

There is no clear answer for this, but the intrinsic value can be determined by the treasury performance. For example, if the treasury could guarantee to back every BHD with 100 DAI, the intrinsic value will be 100 DAI. It can also be decided by the DAO.

## How does the protocol manage to maintain the high staking APY?

Let’s say the protocol targets an APY range of 1,000% to 10,000%, this would translate to a _minimum_ reward yield of about 0.2105%, or a daily growth of about 0.6328%.

If there are 100,000 of BHD staked right now, the protocol would need to mint an additional 632.8 BHD to achieve this daily growth. This is achievable if the protocol can bring in at least $632.80 of daily revenue from bond sales. Even if the protocol doesn't bring in that much revenue, it can still sustain 1,000% APY for a considerable amount of time due to the excess reserve in the treasury.

## Do I have to unstake and stake BHD on every epoch to get my rebase rewards?

No. Once you have staked BHD with BigHeadDAO, your staked BHD balance will auto-compound on every epoch. That increase in balance represents your rebase rewards.

##
