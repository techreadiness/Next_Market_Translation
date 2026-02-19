metaLinks:
  alternates:
    - &gt;-
      https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/getting-started/production-payment-testing
---

# Prod Live Payment Testing

{% hint style=&quot;warning&quot; %}
Only Fiat payments are permitted during live payment testing in the Prod environment.

As live payment testing involves actual transactions, prior consultation and strict adherence to operational guidelines are mandatory.
{% endhint %}

### Live Payment Testing Procedure Guide

This document outlines the live payment testing process conducted in the Prod environment.

* <mark style="color:$danger;">**No separate testing cost support is provided**</mark> for live payment testing.
*   Testing proceeds in the following sequence:

    &gt; **Pre-share Test Plan → Next Market Review &amp; Consultation → Test Execution → Result Sharing → (If necessary) Payment Cancellation Processing**

### 1. Pre-share Test Plan (Required)

The following items must be compiled and **shared with Next Market at least 3 business days prior to the desired test date**.

| Items to Provide        | Description                                                                                                                                                                                                                                                                     |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Test Scope       | <ul><li>Target Store</li><li><p>Product Category</p><ul><li>B2C/C2C Classification</li><li>Product Name or sale_id</li></ul></li></ul>                                                                                                                                                                                               |
| Test Payment Method Information | <ul><li><p>Enter payment method information to be used during testing</p><ul><li>Card Information </li><li>Corporate Card/Personal Card</li><li>Card Name</li></ul></li></ul><p>⚠️ Cancellation policies vary by payment method. Please review <a href="production-payment-testing.md#undefined-3">cancellation policies</a> and <a href="production-payment-testing.md#undefined-1">eligible payment methods</a>.</p> |
| Test Payment Details | <ul><li>Desired Number of Payments </li><li>Desired Cancellation Status</li></ul>                                                                                                                                                                                                                                                |
| Test Schedule Information    | Scheduled Test Date and Time                                                                                                                                                                                                                                                                            |
| Test Account Information    | Test Account GUID                                                                                                                                                                                                                                                                                    |

#### Payment Notes 

**\[ Payment Country and Currency Settings ]** \
You can select the payment country and currency through the **Billing Address information settings** within the payment screen. Please set the country you wish to test first before proceeding with payment.

**\[ Country-Specific Payment Restrictions ]**\
For certain countries and payment methods, **payments using credit cards issued in Korea may be restricted**. Please verify the following details before conducting payment tests or actual transactions.

* **Taiwan**
  * Payment Method: **MyCard**
  * Payments using credit cards issued in Korea are not supported.
* **United States**
  * Payment Method: **Payletter / Coda**
  * Payments with credit cards issued in Korea are not supported.

\
If you need to test international payments, please prepare a payment method issued in the relevant country or a supported alternative payment method in advance.

#### Payment Methods Supported for Cancellation

| Region (Billing Location) | Product Currency                      | Payment Method                                                                        |
| -------- | --------------------------- | ---------------------------------------------------------------------------- |
| Korea       | KRW                         | Credit Card                                                                         |
| Korea       | KRW                         | Easy Payment                                                                         |
| Taiwan      | TWD                         | <p>Credit Card/Mobile Payment/Electronic Payment Methods provided by<br>MyCard PG ⚠️ MyCard points are not provided and cannot be canceled</p> |
| Global      | USD / JPY / TWD / THB / PHP | <p>PayPal (Credit Card)<br>⚠️ Only PayPal members can make payments when using PayPal</p>                   |

#### Payment Cancellation Policy

* Payment cancellation availability varies by payment method.
* Cancellation is possible only for eligible methods, following pre-agreed procedures.
* If cancellation is not desired, **testing can proceed using non-cancellable payment methods.**
* Cancellation may incur <mark style="color:$danger;">**refund processing fees**</mark>. These refund fees will be jointly borne by the developer and LINE NEXT.

### 2. NEXT Market Review and Consultation

* Review the shared test plan.
* **Confirm the feasibility of conducting actual payment tests**, including payment methods and cancellation eligibility, then share this with the developer.

### 3. Test Execution

#### NEXT Market Preparation

① Set up test products

* Product exposure is based on the set **product launch time**.
* For testing, the product launch time must be **temporarily adjusted to the test time**.

② Maintenance Mode Setup (Recommended)

* Actual payment tests are **conducted only in the Prod environment**.
* **Switching to maintenance mode is recommended** to restrict general user access and allow only the developer to conduct the test. 
* A **maintenance bypass link is provided to developers** to enable testing even during maintenance mode.

{% hint style=&quot;warning&quot; %}
**If Maintenance Mode is Not Set**

Conducting live payment testing without enabling service maintenance mode allows general users to access the payment page and make payments. If testing is required during actual sales periods, user payments may occur. Please consider this when coordinating payment test schedules in advance.
{% endhint %}

#### Developer Testing Procedure

* Conduct actual payment tests based on the **payment methods and transaction volumes** agreed upon in advance.

### 4. Sharing Test Results

* After completing testing, share the following information with Next Market:
  * Test account GUID
  * Payment methods used
  * Payment details (order_id, payment amount)

### 5. Payment Cancellation Processing

* For payment methods that support cancellation, if cancellation is requested, process cancellations for all orders included in the test results.
* Cancellation requests are handled by the Next Market development team.
