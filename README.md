# License site (v6)

Static page, no build step and no backend. Host the whole folder anywhere (IPFS, Netlify, GitHub Pages).

## Files
- index.html: the page. The QR code library is inlined, so there are no other scripts to upload.
- product-image.jpg: your hero image (add it; the filename must match the one in index.html).
- index-orig-bak.html: your original backup.

## Before deploying: edit the SETTINGS block near the bottom of index.html
- PAYMENT_ADDRESS: the single receiving address on Base (your mint contract).
- PRICE_ETH.consumer / PRICE_ETH.commercial: the exact ETH amount for each license, for example "0.03" and "0.08".
  The contract tells the licenses apart by amount, so the two amounts must be different.
- LICENSES: USD prices shown on the page. If you change them, also change the matching text in the HTML.

QR codes stay hidden (and Copy is disabled) until the address is valid and both prices are set and different.

## Notes
- One address for both licenses. The QR amount is the license price times the quantity chosen at checkout, so the contract has to work out what was bought from the total.
- The checkout button opens a sheet with the QR code, quantity selector, exact amount, address and Copy button for the selected license.
- The page cannot see payments. The mint contract is what delivers the NFT.
- The Files app preview on iPhone does not run scripts, so QR codes and addresses will look empty there. Open the page in Safari from a host instead.
