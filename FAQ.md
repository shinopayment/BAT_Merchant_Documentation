# API Integration Q&A Document

## 1. API Documentation Request
**Question:** Could you provide the latest integration API documents for deposit and withdrawal? (Please provide us with WORD or PDF file, thank you)

## 2. API URLs
**Question:** Could you provide the latest integration API URL?

### Staging Environment
<table>
<tr>
<th>API Type</th>
<th>URL</th>
</tr>
<tr>
<td>Deposit Request</td>
<td><code>{DOMAIN}/Deposit/CreateOrder</code></td>
</tr>
<tr>
<td>Deposit Query</td>
<td><code>{DOMAIN}/Deposit/CheckOrderDetail</code></td>
</tr>
<tr>
<td>Withdraw Request</td>
<td><code>{DOMAIN}/Payout/CreateOrder</code></td>
</tr>
<tr>
<td>Withdraw Query</td>
<td><code>{DOMAIN}/Payout/CreateOrder</code></td>
</tr>
<tr>
<td>Balance Query</td>
<td><code>{DOMAIN}/Merchant/GetMerchantBalance</code></td>
</tr>
</table>

### Production Environment
<table>
<tr>
<th>API Type</th>
<th>URL</th>
</tr>
<tr>
<td>Deposit Request</td>
<td><code>{DOMAIN}/Deposit/CreateOrder</code></td>
</tr>
<tr>
<td>Deposit Query</td>
<td><code>{DOMAIN}/Deposit/CheckOrderDetail</code></td>
</tr>
<tr>
<td>Withdraw Request</td>
<td><code>{DOMAIN}/Payout/CreateOrder</code></td>
</tr>
<tr>
<td>Withdraw Query</td>
<td><code>{DOMAIN}/Payout/CheckOrderDetail</code></td>
</tr>
<tr>
<td>Balance Query</td>
<td><code>{DOMAIN}/Merchant/GetMerchantBalance</code></td>
</tr>
</table>

## 3. Callback IP Addresses
**Question:** Could you provide the callback IP for deposit and withdrawal so we can whitelist it?

**Answer:** Deposit and Withdrawal both are having same callback IP
- **BAT Staging IP:** `124.217.246.238`
- **BAT Production IP:** `20.198.240.65, 20.212.168.94`

## 4. Environment IP Information
**Question:** Is the information below in test environment the same as in the production environment?

**Answer:** Can refer to clause 3.
- **BAT Staging IP:** `124.217.246.238`
- **BAT Production IP:** `20.198.240.65, 20.212.168.94`

**Note:** If manual callback is in the BackOffice, there will be a different URL:
- **BAT Staging:** `https://backoffice.oppay88.com`
- **BAT Production:** `https://backoffice.battt.io`

## 5. Channel Status
**Question:** Is the channel code currently open and running?

### Deposit Channels
<table>
<tr>
<th>Channel Code</th>
<th>Channel Name</th>
</tr>
<tr>
<td>BMR</td>
<td>Online Banking</td>
</tr>
</table>

### Withdrawal Channels
<table>
<tr>
<th>Channel Code</th>
<th>Channel Name</th>
</tr>
<tr>
<td>LB</td>
<td>Local Bank</td>
</tr>
</table>

## 6. Deposit Failed Callback
**Question:** When "deposit failed," do you support automatic callback?

**Answer:** Yes, with a maximum of 9 attempts. Manual callbacks are also supported.

## 7. Deposit Success Callback
**Question:** When "deposit success," do you support automatic callback?

**Answer:** Yes, with a maximum of 9 attempts.

## 8. Withdrawal Failed Callback
**Question:** When "withdrawal failed," do you support automatic callback?

**Answer:** Yes, with a maximum of 9 attempts. Manual callbacks are also supported.

## 9. Withdrawal Success Callback
**Question:** When "withdrawal success," do you support automatic callback?

**Answer:** Yes, with a maximum of 9 attempts.

## 10. Deposit Amount Decimal Support
**Question:** Does the deposit amount support 100.1 non-integers? If supported, how many decimal places?

**Answer:** Supported, but decimal places are limited to a maximum of 2 digits.

## 11. Withdrawal Amount Decimal Support
**Question:** Does the withdrawal amount support 100.1 non-integers? If supported, how many decimal places?

**Answer:** Supported, but decimal places are limited to a maximum of 2 digits.

## 12. Merchant Balance Inquiry Decimal Support
**Question:** Does the merchant balance inquiry support 100.1 non-integers? If supported, how many decimal places?

**Answer:** Supported, but decimal places are limited to a maximum of 2 digits.

## 13. Fee Calculation and Rounding
**Question:** How do you calculate the fee of deposit or withdrawal? to which decimals? and how to round the numbers? Ex: 18.8847, which number should we display?

**Answer:** Will calculate based on the fees set in the BackOffice, to 2 decimal places

**Examples:**
- 18.8847 will display as 18.88
- 18.8857 will display as 18.89

## 14. Deposit Channel Unique Amounts
**Question:** Does the deposit channel have unique amounts?

**Answer:** Yes, we have

## 15. Withdrawal Channel Unique Amounts
**Question:** Does the withdrawal channel have unique amounts?

**Answer:** No

## 16. Deposit Amount Adjustment
**Question:** Will the deposit submission amount be adjusted, causing inconsistency with the actual amount?

**Answer:** Deposit will be inconsistent, provided that if the channel uses BQR or MOMO, BMR will be consistent.

## 17. Withdrawal Amount Adjustment
**Question:** Will the withdrawal submission amount be adjusted, causing inconsistency with the actual amount?

**Answer:** Withdrawal will be consistent

## 18. Deposit Fee Rounding Method
**Question:** What is the rounding method for deposit fees? How many decimal places are calculated? (Round to 2 decimal places, unconditional round up to 3 decimal places, round down to 1 decimal place...)

**Answer:** Round to 2 decimal places

## 19. Bank List for Deposit
**Question:** Can you please provide the bank list for the "deposit"?

**Answer:** Please refer to the Merchant Integration Guide Bank Appendix

## 20. Bank List for Withdrawal
**Question:** Can you please provide the bank list for the "withdrawal"?

**Answer:** Please refer to the Merchant Integration Guide Bank Appendix

## 21. Settlement vs Payout API
**Question:** Is settlement the same API as payout? If not, does settlement have an independent API? If there is an independent API, please provide the submission and query URLs.

**Answer:** Refer to Clause 2

## 22. Error Codes
**Question:** Please provide the error codes (error code) returned when the "collection" channel encounters an exception, for example:

**Answer:** Please refer to the Merchant Integration Guide Error Appendix
