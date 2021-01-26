# Income-Tax-Simulator

The Income Tax Simulator helps you compare between the Old and New Indian Income Tax Regimes by seamlessly configuring your savings and tax benefits.

## Releases

**Current Release:** v1.1.0

**Master Branch for Development:** [master](https://github.com/chintanr97/Income-Tax-Simulator)

## Downloading the Simulator

Download the simulator from `src` folder of the project root directory or alternatively `git clone` the repository and open the simulator in `Microsoft Excel` locally.

## Understanding the inputs

### Different Components of the Income

1. **Annual Salary:** The current annual in-hand salary based on the ongoing financial year.
2. **Basic Component + Dearness Allowance (per month):** It is the amount received *per month* in the slab of `Basic Component` and `Dearness Allowance` combined. Please note that the `Dearness Allowance` is not same as `Special Allowance`. The value in this cell is used to calculate contributions to the the Employee Provident Fund (EPF) account.
3. **Date of Joining:** If you have joined the organization in between of a financial year, then you must alter it accordingly - in the format of `DD/MM/YYYY`. Please note, that any of your previous employer's income can be provided in the point 7. By default it corresponds to the start date of current financial year, i.e. `01/04/2020`.
4. **Joining Bonus:** Applicable if you have joined the organization newly.
5. **Provident Fund Contribution Rate:** The value in percentage (default is `12%`) indicating the contribution rate into employee's EPF account, each by the employee and the employer, as applicable from organization policies.
   * **Employer's contribution within Annual Salary (Yes/No):** Mostly the employer's contribution to employee's EPF account is considered within the CTC associated in the offer letter and decuted from the `Special Allowances` bracket of the `Annual Salary`. Check the monthly pay slip for further details.
6. **Voluntary Provident Fund Contribution Rate:** The value in percentage, indicating employee's voluntary contribution to the EPF account. The input is considered to be capped at `100%` over and above the mandatory PF contribution rate as added in point 5.
7. **Previous Employer's Income:** The amount earned from any previous positions within or outside the organization in the current finanacial year, i.e. `FY 2020-2021`.
8. **Income from Dividends:** The amount of dividend earned in the current financial year for the shares held within India or under any Foreign Stock Exchange. The amount must be entered without any tax deductions at source and will be taxed appropraitely using the applicable slab rates.
   * Tax deductions at source, on dividends earned from domestic companies is applied at a rate of `7.5%` for the `FY 2020-2021` and will be adjusted while calculating the gross taxable income.
   * Tax deductions at source, on dividends earned from foreign companies can be added as reimbursements under Section 90 or 91 based on the applicability of the double taxation treaty with the foreign country.
9. **Income from Capital Gains:** The amount earned as a gain under capital assets.
   * **Short Term Capital Gains (STCG):** These capital gains can be divided into 2 catgories, those which are applicable under Section 111A and those that are not. STCG applicable under Section 111A are taxed at a rate of `15%` with additional applicable surcharge and cess rates. If the STCG are not listed under Section 111A then they will be considered as a source of other income and taxed at normal applicable slab rates.
   * **Long Term Capital Gains (LTCG):** The LTCG arising on sale of equity shares (as applicable under Section 112A) are taxed at a rate of `10%` if the gains exceed `INR 1,00,000`. Any other LTCG, would be taxed at a rate of `20%` - other than some specified capital assets, for which the taxpayer can choose one of the following options:
     * Use indexation benefit and pay tax on LTCG (not applicable under Section 112A) at a rate of `20%`.
     * Do not use indexation benefit and pay tax on LTCG (not applicable under Section 112A) at a rate of `10%`.

   The capital gains must be manually adjusted against any *capital loss* as applicable by the income tax rules. Capital losses can be adjusted only under the head of capital gains i.e., Short term capital losses can be adjusted against both STCG and LTCG, but Long term capital losses can be adjusted against only LTCG. Both, short term and long term capital loss can be carried forward for `8 Assessment Years` immediately following the Assessment Year in which the loss was first computed. 
   
   The income under STCG (applicable under Section 111A) and LTCG can be adjusted against the basic exemption limit (`INR 2,50,000`, for individuals of the age < 60) after complete adjustment of gross taxable income. The simulator works on an optimal function to choose a best path in adjusting these capital gains against the basic exemption limits.
10. **Any other Income:** This includes any interest earned on savings bank account or recurring deposits, any taxable reimbursements, etc.

### Tax Benefits (applicable in Old Regime)

1. **House Rent Allowance (HRA):** The HRA exemptions in the tax calculations are applied based on the minimum of the following values:
   * Acutal HRA received
   * `50%` of `Basic + DA Component`in metro cities and `40%` for non-metro cities
   * The value of the formula: `[Acutal Rent Paid] - [10% of Basic + DA Component]`
2. **Leave Travel Allowance (LTA):** The LTA exemptions are applied based on the income tax policies. Please refer the LTA guidelines published by your organization.
3. **Profession tax:** The annual amount paid as profession tax, depending upon the city of employment in the financial year. It can found from the annual tax deduction slip shared by the employer.
4. **Children's Education and Hostel Allowance:** The deductions of children's education allowance are capped at `INR 100` per month and children's hostel allowance are capped at `INR 300` per month. The maximum deductions can be obtained for upto 2 children, by each of the parents.
5. **Section 80C/80CCC/80CCD(1) Investments:** The deductions under these slabs are cumulatively capped at `INR 1,50,000`. However, the input can be added as much as the investments and the formula will adjust it to the income tax policies based on the value entered.
6. **Section 80CCD(1B):** Denotes the investments that can be made to employee's National Pention Scheme. The deductions in the slab are capped at `INR 50,000`.
7. **Section 80D:** Premium paid for insurance policies. The amounts are capped respectively based on the claims provided and the income tax policy. Claims can only be made to one of the following sections in the policy: `Parents`or `Parents as Senior Citizens`.
8. **Section 80DD/80DDB:** Allows deductions for prescribed or severe medical treatments (based on the income policy) for either dependents or self. Please note that the claims made under this section are only applicable if no claims are added under Section 80U of the income tax.
9. **Section 80E:** Deductions allowed for interest on education loan for higher education. The loan can be taken for self, spouse, or children for whom the taxpayer is the legal guardian. The maximum limit on the deductions is upto complete amount of interest paid in the ongoing FY.
10. **Section 80EE/80EEA:** Deductions applied for house loans. The benefits can be claimed in only of the applicable policies, i.e. either 80EE or 80EEA in a given FY.
11. **Section 80EEB:** Deductions applicable for loan on electric vehicles as described in the income tax policies.
12. **Section 80G/80GGA:** Deductions applicable for the donations made as per the income tax policies.
13. **Section 80TTA:** Interest earned from savings bank account (SBA) in the FY needs to be added as additional income in the point 9 from different components of income above. The amount can then be added a deduction under this section. The maximum tax benefit on SBA interest is capped at `INR 10,000`.
14. **Section 80TTB:** Interest earned on various deposits can be added for deductions in this slab, provided you are a `Senior Citizen` based on the income tax policies. The maximum deduction allowed is capped at `INR 50,000`.
15. **Section 80U:** Deductions applicable for the treatment of self disability. The claims under this section can only be added when no claims are made under Section 80DD. In both of these sections, the claims can be made as much maximum amount (providing a valid disability certificate), whereas deductions under Section 80DDB are capped minimum of either the maximum cap or the actual expense incurred.

These benefits or tax deductions are not applicable in the New Income Tax Regime. However, the difference in the income tax rates between the 2 regimes allow taxpayers to adjust between their investments while staying in old regimes with higher tax rates or moving to new regime without any tax deductions and incurring less tax rates.

### Some additional tax benefits

1. **Loss From House Property:** These deductions include the amount as applicable because of the *loss of income* (as defined under IT policies) due to payment of interest on the house loan taken on the property owned. The deductions under this section are *not applicable* in the New Tax Regime. However, any loss due to payment of interest on house loan can be adjusted under income due to the house property (e.g. a let-out house property). Although, this clause cannot be used as a deduction under *loss of income due to house property*, in the New Income Tax Regime.
2. **Section 10 Deductions:** Section 10 deductions include the benefits under various clauses applicable under the Old Income Tax Regime. In the New Income Tax Regime an individual can only claim deductions under clause 10(14) of the Income Tax Rules.

### Tax benefits on dividend income

1. **Section 90:** Tax deducted by foreign countries, which have a bilateral treaty with India, can be added for reimbursement under Section 90 to avoid double taxation. Please check the DTAA agreement and the applicability of the treaty for the foreign countries in which shares are hold for earning dividends.
2. **Section 91:** Tax deducted by foreign countries, which do *not* have a bilateral treaty with India, can also be reimbursed to save double taxation. However, in this case the terms should be met as added in the Section 91 of the Income Tax Act.
3. **Deductions for interest paid to earn dividends:** If the taxpayer has borrowed money to specifically invest in earning income from dividends, then the interest paid on the borrowed amount can be used for deduction on `Gross Dividend Income`. The maximum deduction applicable under this rule is capped at `20%` of the gross dividend income (including domestic and foreign dividend income).

## Policy of Usage

The simulator is only an indicative to the income tax amount that you might have to pay based on either of the tax regimes. The actual amount of income tax depends upon the income available in Form 26A and all the investments made during the FY, while filing the Income Tax Return (ITR).
