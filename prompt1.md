# Prompt 1 (no accessibility mentioned)

Build a single-page Pizza Ordering Form web app. Use plain HTML/CSS/JavaScript only (no frameworks, no build tools). Deliver as one self-contained index.html that runs locally when opened in a browser. Mock any behavior that would normally require server-side processing.

Core requirements

Create a clean UI with these sections:

1. Customer info

* Full name (required)
* Email (required; must be valid format)
* Phone (optional)
* Order type (required): Pickup or Delivery
* If Delivery is selected, show Delivery Address fields (required):
  * Street
  * City
  * State/Region
  * Postal code

2. Pizza builder

* Size (required): Small, Medium, Large
* Crust (required): Thin, Hand-tossed, Deep dish, Gluten-free (+$2.00)
* Sauce (required): Tomato, Alfredo (+$1.00), Pesto (+$1.50)
* Cheese level (required): Light, Normal, Extra (+$1.00)
* Toppings (0+): Pepperoni, Sausage, Mushrooms, Onions, Green peppers, Olives, Pineapple
* Each topping +$0.75
* Quantity (required): integer 1–10

3. Extras

* Breadsticks (+$4.00)
* Soda (+$2.00)
* Salad (+$5.00)

4. Special instructions

* Free-text (optional, max 200 characters) with a visible character counter.

5. Payment

* Payment method (required): Card or Cash
* If Card is selected, show fields (required):
  * Name on card
  * Card number (validate length 13–19 digits; allow spaces/dashes in input)
  * Expiration (MM/YY, validate plausible date not in the past)
  * CVV (3–4 digits)
* If Cash is selected, show “Cash on delivery/pickup” message and hide card fields.

Pricing rules

* Base pizza prices:
  * Small $10.00
  * Medium $12.00
  * Large $14.00
* Add-ons:
  * Gluten-free crust +$2.00
  * Alfredo sauce +$1.00
  * Pesto sauce +$1.50
  * Extra cheese +$1.00
  * Each topping +$0.75
* Extras:
  * Breadsticks $4.00
  * Soda $2.00
  * Salad $5.00
* Delivery fee:
  * If Delivery: +$3.00
* Tax:
  * 8.5% applied to subtotal + delivery fee
* Total:
  * (pizza line total * quantity) + extras + delivery fee, then tax, then grand total

Operational behavior

* Show a live “Order Summary” panel that updates instantly as the user changes selections:
  * Customer name (or “—” if empty)
  * Order type (Pickup/Delivery)
  * Pizza configuration (size/crust/sauce/cheese)
  * Toppings list (or “None”)
  * Quantity
  * Extras list (or “None”)
  * Pricing breakdown: Subtotal, Delivery fee (if any), Tax, Grand total
* Use inline validation:
  * Required fields should show a clear error message when invalid.
* On submit:
  * Prevent default navigation.
  * Show a confirmation view (in-page, not an alert) that includes:
    * An order number (random 6-digit)
    * Timestamp (local time)
    * Full order summary and totals
  * Provide a “Start New Order” button that resets the form and returns to the form view.

Code quality expectations

* Keep code well-structured:
  * Separate logic into functions (pricing, validation, rendering summary, submit handling).
  * Avoid global variables where possible.
  * Add brief comments explaining the main logic.
  * Use responsive layout so it looks reasonable on mobile and desktop.