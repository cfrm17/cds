# Credit Default Swap Model

Credit trading focuses on securities which have cashflows contingent on one or more defaults of risky securities, including bonds, loans, FRNs, etc. Credit default swap is a type of credit instruments, with which the buyer can protect the principal of debt investment by paying a fixed rate fee periodically until default. This paper documents the pricing theory of the credit default swap.   

W assume that the buyer of credit default swap buys a protection of the bond principal by paying a fixed rate fee to the protection seller periodically until the default event happens. When default happens, the protection seller simply buys the bond and pays the buyer the notional of the bond. But this transaction may occur immediately at default time or postponed to next payment date. 

For bonds with various seniorities, their recovery values are usually different. In general, bonds with higher seniority would have higher recovery value. This means that when default happens, the bond can be still traded on the market of a proportion of its par value. The protection value bought by the credit buyer is actually a proportion of the par value depending on the seniority of a security. 

A credit default swap is actually an option (see https://finpricing.com/lib/FxCompound.html), which protect the buyer against possible default of an entity, the so-called reference entity. To accomplish this, the buyer of the default swap pays the seller a premium periodically in exchange for a contingent payment in case the reference entity defaults. The contingent payment is the difference between the notional of the swap and the recovery value from the reference entity. When default happens, the buyer of the swap receives the contingent payment from the seller and stops any future payments.

To value a credit swap, it is similar to value interest rate swaps under the no-arbitrage principle. The cashflows of fixed rate fees and the value of protection, after adjustment of default probability, are discounted to the present, with the difference being the mark-to-market value of the swap. 

In some swaps, the buyer has to pay the accrued premium for the current period if default happens between two payment dates. 

The model assumes two ways to settle the payments. One is to settle all the cash flows when the default happens. The other is to settle all the cash flows on the next payment date. 

Let the default time of a bond be  ; we assume a deterministic risk-neutral hazard rate,  , such that  . With this definition, the survival probability, cumulative distribution function and survival density function are as in the following 

	 ,   and  ,  .

In the model, the hazard rate is assumed of being flat, i.e.  is a constant. But the general principle discussed in the following sections works for general structured hazard models. 

Suppose the bond pays cash flows at nodes   and  is the last payment time. The current time is  . If the bond defaults in the interval  , the amount of  unit is paid to the swap buyer either at default or at the next payment date,  , depending on the definition of the contract, where   is the recovery rate. Suppose   is the discount factor at time t, then the protection value is 

(1)	 ,  

where   if payment is made at default time and   if payment is made at the next payment date, for all  .  

The total protection value of the swap is the sum of the protection values in each of the payment intervals. 

The swap buyer often pays a fee based on a fixed premium rate at the end of each payment interval if the reference entity does not default in the interval. In the case when default happens, the option buyer receives the contingent payment of the protection and stops the fee payment. The option buyer may need to pay the accrued fee amount in the period before default, depending on the contract specification. Similar to the protection payment, the accrued fee may be paid at default or next payment date.
 
Suppose the bond survives the interval  . It must have survived all the preceding intervals. The amount of fee that is proportional to the day fraction of the current payment interval is paid out

	 ,

where   is the fee rate and   is the day fraction of current payment interval with the given day count convention. 

When default happens in the interval  , the accrued fee is proportional to the fraction of days from the starting of the current payment period to the default date. In general, the present value of accrued fee is 

	 .

The present value of the overall fee is  

(2)	 ,

where   is fee is accrued and 0 otherwise. 

The credit swap value to the contract buyer is the difference between the protection value and the fee value. The value of the credit swap to the buyer is 

(3)	 

In calculating the swap value, the current model assumes that the hazard rate is a flat rate  , which is constant over the lifetime of the contract. The zero rate in each of the integral intervals can also be assumed to be flat such that the integrals can be calculated using explicit formulas. 

Let   and  for  ,  ,  and  . Then we have 

(4)	 
(5)	 
(6)	 
(7)         

In general, the current value time is assumed to be zero. The survival density satisfies , if  . So when the valuate date is in the middle of an accrual interval, the last two formulas (6-7) above should be modified, as  . We have 

(8)	 

which is the weighted average length of the accrual interval.  Similarly, 

(9)     

The abnormality of these two formulas will affect the valuation of accrued fees for the first period. 

To mark-to-market a credit default swap, the only input needed is the hazard rate besides the standard discount curve of interest rate. 


