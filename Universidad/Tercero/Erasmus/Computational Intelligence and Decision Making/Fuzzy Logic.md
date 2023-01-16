#Theory/AI #Laboratory/AI

# Aplications of Fuzzy Logic
- Automotive systems(auto-transmissions, auto-engines...)
- Air Conditioners
- Medical Diagnose Systems
- Domestic Goods

## Difference between Crisp and fuzzy
Crisp logic works in a boolean way True or False, where as Fuzzy works with a range from [0,1] having **membership degrees**, that is intervals.
![[Pasted image 20230103172415.png]]
# Membership Functions
The membership functions determine how the intervals are distributed. These can be combined for example for the image of above 5 membership functions would be used.
![[Pasted image 20230103172625.png]]
![[Pasted image 20230103172638.png]]
![[Pasted image 20230103172913.png]]
In the example we can see how Crisp are either, hot,cold, very cold... But in fuzzy logic they can be both for example partially hot and partially warm as Tx. where as in crisp it is warm.

# Logic operations eg
| Boolean logic | Fuzzy Logic |
| ------------- | ----------- |
| $A\land B$    | min(A,B)    |
| $A\lor B$     | max(A,B)            |
| $\neg A$      |   1-A          |
## Aplying Fuzzification and Inference
There are two main types of fuzzy inference systems:
- Mandani type: Most common it returns a fuzzy set
- Sugeno type: It returns anorher membership function

The inference process has a structure simmilar to:
1. Fuzzification of Input
2. Apply fuzzy operators
3. Imply from the antecedent to the consequence (if-then)
4. Aggregation of the consequents along the rules.
5. Defuzzification

![[Pasted image 20230103174605.png]]
![[Pasted image 20230103174613.png]]
![[Pasted image 20230103174623.png]]
![[Pasted image 20230103174639.png]]
![[Pasted image 20230103174650.png]]
![[Pasted image 20230103174707.png]]
![[Pasted image 20230103174719.png]]

After doing this in the example the next step is ==**Defuzzification**== for that there are some strategies such as Center of Gravity, Bisector, Mean of Maximum, Smallest value of Maximum, Largest value of Maximum.
![[Pasted image 20230103174948.png]]
![[Pasted image 20230103174957.png]]
