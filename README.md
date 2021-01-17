# Income-Tax-Simulator

The Income Tax Simulator helps you compare between the Old and New Indian Income Tax Regimes by seamlessly configuring your savings and tax benefits.

## Releases

**Current Release:** v0.1.0

**Master Branch for Development:** [master](https://github.com/chintanr97/Income-Tax-Simulator)

## Downloading the Simulator

Download the simulator from `src` folder of the project root directory or alternatively `git clone` the repository and open the simulator in `Microsoft Excel` locally.

## Understanding the inputs

### Different Components of the Income

1. **Annual Salary:** The current annual in-hand salary based on the ongoing financial year.
2. **Basic Component + Dearness Allowance (per month):** It is the amount received *per month* in the slab of `Basic Component` and `Dearness Allowance` combined. Please note that the `Dearness Allowance`is not same as `Special Allowance`. The value in this cell is used to calculate contributions to the the Employee Provident Fund (EPF) account.
3. **Date of Joining:** If you have joined the organization in between of a financial year, then you must alter it accordingly - in the format of `DD/MM/YYYY`. Please note, that any of your previous employer's income can be provided in the point 8. By default it corresponds to the start date of current financial year, i.e. `01/04/2020`.
4. **Joining Bonus:** Applicable if you have joined the organization newly.
5. **Provident Fund Contribution Rate:** The value in percentage (default is `12`) indicating the contribution rate into employee's EPF account, each by the employee and the employer, as applicable from organization policies.
6. **Employer's contribution within Annual Salary (Yes/No):** Mostly the employer's contribution to employee's EPF account is considered within the CTC associated in the offer letter and decuted from the `Special Allowances` bracket of the `Annual Salary`. Check your monthly pay slip for further details.
7. **Voluntary Provident Fund Contribution Rate:** The value in percentage, indicating employee's voluntary contribution to the EPF account. The input is considered to be capped at `100 %`over and above the mandatory PF contribution rate as added in point 5.
8. **Previous Employer's Income:** The amount earned from any previous positions within or outside the organization in the current finanacial, i.e. `FY 2020-2021`.
9. **Any other Income:** This includes any interest earned on savings bank account or recurring deposits, any taxable reimbursements, etc.

### Tax Benefits (applicable in Old Regime)

1. **House Rent Allowance (HRA):** The HRA exemptions in the tax calculations are applied based on the minimum of the following values:
   * Acutal HRA received
   * 50% of `Basic + DA Component`in metro cities and 40% for non-metro cities
   * The value of the formula:`[Acutal Rent Paid] - [10% of Basic + DA Component]
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

These benefits or tax deductions are not applicable in the New Income Tax Regime. However, the difference in the income tax rates between the 2 regimes allow taxpayers to adjust between thier investments while staying in old regimes with higher tax rates or moving to new regime without any tax deductions and incurring less tax rates. These benefits leverage out when the surcharge on the gross taxable income increases as per the new tax regime compared to old one.

## Policy of Usage

The simulator is only an indicative to the income tax amount that you might have to pay based on either of the tax regimes. The actual amount of income tax depends upon the income available in Form 26A and all the investments made during the FY, while filing the Income Tax Return (ITR).
