# Project Name: Lending Club Use Case (EDA Assessment - AI/ML Programme - Upgrad)

## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)

<!-- You can include any other section that is pertinent to your problem -->

## General Information
- Problem Statement:
        LENDING CLUB is a consumer finance company which specialises in lending various types of loans to urban customers. When the company receives a loan             application, the company has to make a decision for loan approval based on the applicant’s profile. Two types of risks are associated with the                bank’s decision:

                - If the applicant is likely to repay the loan, then not approving the loan results in a loss of business to the company
                - If the applicant is not likely to repay the loan, i.e. he/she is likely to default, then approving the loan may lead to a financial loss for the company
- Objective: 
        Like most other lending companies, lending loans to ‘risky’ applicants is the largest source of financial loss (called credit loss). The credit loss             is the amount of money lost by the lender when the borrower refuses to pay or runs away with the money owed. In other words, borrowers who default            cause the largest amount of loss to the lenders. In this case, the customers labelled as 'charged-off' are the 'defaulters'.

            Understand the driving factors (or driver variables) behind loan default, i.e. the variables which are strong indicators of default. The company can utilise this knowledge for its portfolio and risk assessment.

## Conclusions
    - Observations - Low Risk Factors:
            -    Amount in the range of 5000 to 14,000
            -    For borrowers with annual income greater than 90,000
            -    For purposes like weddings, car purchase, credit card are low risk
            -    Which can be disbursed under Grade-'A' or Grade-'B'
            -    For borrowers with their DTI score less than or equal to 10
            -    For borrowers with their public bankruptcy record count being 0 </span>
    - Recommendations - Low Risk Factors::
            -    Loan requests meeting 3 or more of the above points can be considered to be a  medium risk
            -    Loan requests meeting all factors are best fit for loan acceptance

    - Observations - High Risk Factors:
            -    Amount greater than 21,000
            -    For borrowers with annual income less than 45,000
            -    For purposes like small business, renewable energy and educational
            -    Which need to be approved only under Grade-'D', Grade-'E', Grade-'F' and Grade-'G'
            -    For borrowers with their DTI score 2.
            -    For borrowers with DTI score greater than 2 are best avoided
            -    For borrowers with their public bankruptcy record count greater than 0
    - Recommendations:
            -    Loan requests meeting 3 or more of the above points will have a higher chance of defaulting
            -    Loan requests meeting all the above factors should not be considered for loan acceptance

## Technologies Used
- numpy  - version 1.23.5
- pandas - version 1.5.3
- matplotlib - version 3.7.0
- seaborn - version 0.12.2
- colorama - version 0.4.6

## Acknowledgements
This project is an assessment exercise designed ad integratd into AI/ML programme at UpGrad in collabaration with IIIT-B


## Contact
Created by [@techexorcist] - feel free to contact me!


<!-- Optional -->
<!-- ## License -->
<!-- This project is open source and available under the [... License](). -->

<!-- You don't have to include all sections - just the one's relevant to your project -->
