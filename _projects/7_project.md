---
layout: page
title: IFRS 17 Calculation Engine
description: Open source implementation of the new economic accounting standard
img: assets/img/ifrs17CE.jpg
importance: 5
category: work
---

I am developer of the Systemorph open-source International Financial Reporting Standard 17 (**IFRS 17**) calculation engine. 
The goal is to provide insurance companies a solution which everyone can utilize along with real data in order to enable 
much richer and realistic discussions about the new standard and a better idea of how to interpret and compare different results. 

Development of the calculation engine required an in-depth study of the new principle-based economic accounting standard
that has become effective since January 2023, and impacts all legal entities that write insurance contracts.
In its nature, **IFRS 17** is a valid initiative to make insurer's financial statements more comparable, as it introduces
economic valuation of portfolios. It also attempts to make profitability more representative of the company current 
financial situation, since it regulates how the profit and loss must be recognized and allocated to each financial period.

New reporting standards for insurance companies have a big impact on their virtual performance. 
For investors it is very important to understand both the new reporting standard and how to interpret the resulting numbers.
For this reason, as a sub-project, I also contributed to the development of a tool, that with a simplified model approximates balance sheets 
of some company both under the combination of **IFRS 9** for assets and **IFRS 17** for liabilities as well as under the combination 
**IAS 39** and **IFRS 4**. At the end we provide a report, which helps to interpret the results.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/EquityChangeIFRS17.png" title="Shareholder Equity Change" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Both computed equities are reported, together with the contractual service margin and its sum with the equity under the new reporting standards. 
These numbers provide insight on the difference that the new standards bring. In general the Shareholders' equity under IFRS 17 is reduced, 
mainly for the reason that the estimated profit of the future cashflows (contractual service margin) should not be subtracted from the liabilities. 
Hence the sum of the equity and the contractual service margin is interesting to shareholders, and it is often greater than the equity under the previous reporting standards. 
The main reasons are that the liabilities are now discounted and the invested assets are reported at their market (fair) value.    
</div>

The main change that IFRS 17 introduces is that the expected gains of profitable insurance policies cannot be realized 
in the present but need to be reported as a part of liabilities called the **contractual service margin**. 
As a result, the liabilities of insurance companies virtually increase compared to the previous reporting standard IFRS 4. 
On the other hand, on the asset side the main change coming with IFRS 9 is that companies need to report the current value of the invested assets, 
the so called **market value**, which is in most cases higher than the originally invested amount, called the **book value** 
(note that asset losses have to be realized soon after ocurrence through an impairment). 

These combined changes result in the change of the shareholders' equity. This matters as the shareholders' equity 
is a major indicator of a companies financial stability, its value, and its attractiveness to investors. 
A change in this quantity due to a new accounting standard (rather than a change in business) causes quite some attention and requires an explanation.


