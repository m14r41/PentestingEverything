

### **Application Logic Flaws**

| **Aspect**                   | **Details**                                                                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Description**              | Application Logic Flaws occur when a web application's normal logic or workflow can be manipulated, allowing attackers to bypass security measures or misuse functionality in unexpected ways. |
| **Conditions to be Vulnerable** | - Inadequate validation of user actions or state transitions. <br> - Assumptions about the sequence of operations in workflows (e.g., checkout, registration). <br> - Missing checks for user privileges when performing sensitive actions. |
| **Where to Find**            | - Shopping carts that allow price modifications. <br> - Account registration processes missing verification steps. <br> - Applications with multi-step processes that do not enforce a strict workflow order. |
| **Common Exploits**          | - **Changing a product price to a negative value**: An attacker manipulates the price of an item to a negative number (e.g., `-100`), resulting in a credit to their account instead of a charge. <br> - **Skipping payment steps**: The attacker submits an invalid or modified payment form to skip or reduce the amount due. <br> - **Bypassing input validation**: Manipulating workflow parameters (e.g., submitting incomplete or unexpected values) to bypass checks, such as registering without verifying an email address. |
| **Example**                  | An attacker manipulates a "price" parameter in an e-commerce site to change the final cost of a product. URL: `http://example.com/cart?product_id=123&price=-100` <br> The attacker receives a refund or discount instead of paying for the item, due to a logic flaw in price validation. |

---


### **Application Logic Flaws - Digit Manipulation Payloads**

| **Payload Type**             | **Example Payloads**                                                                                                         | **Description**                                                                                                                                                   |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Negative Number Manipulation** | - `price=-1` <br> - `quantity=-5`                                                                                          | Attacker submits a negative value for a field (e.g., price or quantity), potentially resulting in a refund or bypassing limits, if the application doesn’t handle negative numbers. |
| **Oversized Input**            | - `price=9999999999` <br> - `discount=500`                                                                                  | Submitting an abnormally high number to exploit the system's handling of large integers. For example, large discounts or price reductions may not be capped appropriately. |
| **Decimal Exploits**           | - `price=0.01` <br> - `price=0.00001`                                                                                       | Manipulating decimal values to exploit rounding or precision errors in payment calculations, potentially leading to purchasing items for less than their intended value. |
| **Zero Value Inputs**          | - `price=0` <br> - `quantity=0`                                                                                             | Bypassing payment or other validation steps by setting values to zero, exploiting applications that don't properly validate non-zero inputs for sensitive operations. |
| **Boundary Testing**           | - `quantity=9999` <br> - `price=999999999`                                                                                   | Testing the upper or lower limits of input fields to determine how the application handles edge cases. For example, a quantity too high might cause unexpected behavior in processing orders. |

