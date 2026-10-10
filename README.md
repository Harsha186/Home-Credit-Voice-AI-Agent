Home Credit – AI Voice Agent  for Loan Against Property Qualification

## Overview:  
 This repository contains the system prompt architecture, conversation state flow, and evaluation test cases for an outbound AI Voice Agent designed for Home Credit. The agent contacts existing loyal customers to qualify them for a pre-approved Loan Against Property (LAP) offer up to ₹75,00,000 before initiating a human handoff.

TEST – 1: Happy Path(Full Pass)
user: Hello. 
agent: Hello, am I speaking with Harsha?
user: Yes. 
agent: As a valued Home Credit customer, you're pre-approved for a Loan Against Property of up to ₹75 Lakhs. I just need a few quick details to confirm preliminary eligibility—shall we proceed?
user: Yes. Of course, you can. 
agent: What type of property is it: residential, commercial, or industrial?
user: It's residential. 
agent: Is the property in your sole ownership or jointly owned?
user: Sole ownership. 
agent: Do you have the original property documents available for verification?
user: Yes. I have 
user: original documents available. 
agent: How much loan amount are you looking for?
user: Seventy five lakhs. 
agent: What is your occupation, and is your income credited to your bank account rather than received in cash?
user: I am a bank employee. I am salaried, my income is created directly to my bank account. 
agent: What’s the estimated current market value of the property?
user: One point two crore. 
agent: What loan tenure would you prefer, between 3 and 15 years?
user: Ten years. 
agent: Congratulations, Harsha! Based on the preliminary details provided, your profile qualifies for the offer. I’m forwarding your file to our Senior Loan Expert, who’ll call you shortly to discuss interest rates and documentation. Thank you for choosing Home Credit, and have a wonderful day!
user: Thank you. 
agent: You're welcome. Have a great day.

TEST – 2: Immediate Disqualification(Agricultural Property)
user: Hello? 
agent: Hello, am I speaking with Harsha?
user: Yes. 
agent: I’m Amritanshu from Home Credit regarding your account with us. As a loyal customer, you’re pre-approved for a Loan Against Property of up to ₹75 lakhs; may I ask a few quick eligibility questions?
user: Yes. 
agent: What type of property is it: residential, commercial, or industrial?
user: It is agricultural land. 
agent: Thank you for the information. Unfortunately, under our current policy for this pre-approved offer, we’re unable to proceed as the criteria aren’t met. Thank you for your time with Home Credit.
user: Thank you. 
agent: You’re welcome. Have a good day.

TEST – 3: Loan Transfer Switch
user: Hello. 
agent: Hello, am I speaking with Harsha?
user: Yes. You are. 
agent: I’m Amritanshu, calling from Home Credit regarding your account with us. As a loyal customer, you’re pre-approved for a Loan Against Property of up to ₹75 lakhs; may I ask a few quick eligibility questions?
user: Actually, I already have an existing loan on this property, and I want to reduce my EMI. 
agent: Thank you for sharing that. Since you already have an existing loan on the property, our dedicated Loan Transfer Specialist will review your EMI reduction options and call you shortly. Thank you for your time with Home Credit.
user: Thank you. 
agent: You’re welcome. Have a good day.

TEST – 4: Loan Amount greater than 75 lakhs 
user: Hello. 
agent: Hello, am I speaking with Harsha?
user: Yes. You are. 
agent: I’m Amritanshu, calling from Home Credit regarding your account with us. As a loyal customer, you’re pre-approved for a Loan Against Property of up to ₹75 lakhs; may I ask a few quick eligibility questions?
user: Yes. Let's proceed. 
agent: What type of property is it: residential, commercial, or industrial?
user: Residential. 
agent: Is the property in sole ownership or joint ownership?
user: It's in sole ownership. 
agent: Do you have the original property documents available for verification?
user: Yes. I have. 
agent: How much loan amount are you looking for?
user: I need ninety lakhs. 
agent: Our current pre-approved offer is capped at ₹75 lakhs. Would you like to proceed with the maximum eligible amount of ₹75 lakhs?
user: Yes. That's what works for me. 
agent: What’s your occupation, and is your income credited to your bank account rather than received in cash?
user: Yes. I am salaried with bank credit. 
agent: What’s the estimated current market value of the property?
user: One point two crore. 
agent: What loan tenure would you prefer, between 3 and 15 years?
user: It's ten years. 
agent: Congratulations, Harsha! Based on the preliminary details, your profile qualifies for the offer. I’m forwarding your file to our Senior Loan Expert, who’ll call you shortly to discuss interest rates and documentation. Thank you for choosing Home Credit.
user: Thank you. 
agent: You’re welcome. Have a wonderful day.

TEST – 5: Busy Customer
agent: Hello, am I speaking with Harsha?
user: Hello. 
user: Yes. But I am in a urgent meeting right now and cannot talk. 
agent: I completely understand. What would be a convenient date and time for us to call you back?
user: Please call me back tomorrow at four PM. 
agent: All right, I'll call you back tomorrow, Sunday, October 11, at 4 PM. Goodbye.


TEST – 6: Immediate Disqualification(Cash Salary)
user: Hello. 
agent: Hello, am I speaking with Harsha?
user: Yes. You are. 
agent: I’m Amritanshu, calling from Home Credit regarding your account with us. As a loyal customer, you’re pre-approved for a Loan Against Property of up to ₹75 Lakhs; may I ask a few quick eligibility questions?
user: Of course. 
agent: What type of property would you like to pledge: residential, commercial, or industrial?
user: Residential. 
agent: Is the property in your sole ownership or jointly owned?
user: Sole ownership. 
agent: Do you have the original property documents available for verification?
user: Yes. I have. 
agent: How much would you like to borrow, up to ₹75 Lakhs?
user: Seventy five lakhs. 
agent: What’s your occupation, and is your income credited to your bank account rather than paid in cash?
user: No. I run a shop, but all my earnings are taken in cash. 
agent: Thank you for the information. Unfortunately, based on our current policy for this pre-approved offer, we’re unable to proceed further at this time as the criteria aren’t met. Thank you for your time with Home Credit.
user: Thank you. 
agent: You’re welcome. Have a good day.

TEST – 7: Handling out-of-order answers
user: Hello. 
agent: Hello, am I speaking with Harsha?
user: Yes. You are. 
agent: As a valued Home Credit customer, you’re pre-approved for a Loan Against Property of up to ₹75 lakhs. I just need a few quick details to check eligibility—shall we proceed?
user: Yes. Of course. 
agent: What type of property is it: residential, commercial, or industrial?
user: It's a residential property jointly owned with my brother, and the market value is around one point two crore. 
agent: Are the original property documents available for verification?
user: Yes. I have original documents. 
agent: How much loan amount are you looking for?
user: I need forty five lakhs 
agent: What’s your occupation, and is your income credited to your bank account?
user: I am self employed and receive all my payments in my bank bank account. 
agent: What loan tenure are you looking for, between 3 and 15 years?
user: Seven year tenure. 
agent: Congratulations, Harsha! Based on the preliminary details provided, your profile qualifies for the offer. I’m forwarding your file to our Senior Loan Expert, who’ll call you shortly to discuss rates and documentation. Thank you for choosing Home Credit, and have a wonderful day!
user: Thank you. 
agent: You’re welcome. Have a good day.
