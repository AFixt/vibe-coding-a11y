# Prompt 2 (same form + explicit accessibility requirements)

Build a single-page Pizza Ordering Form web app. Use plain HTML/CSS/JavaScript only (no frameworks, no build tools). Deliver as one self-contained index.html that runs locally when opened in a browser. Mock any behavior that would normally require server-side processing.

Implement the exact form, pricing rules, and behaviors described below and meet the accessibility requirements at the end.

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

Accessibility requirements (must implement)

This must meet-or-exceed all requirements for WCAG 2.2 Level AA. The below requirements are not the only accessibility requirements, but are indicative of the types of accessibility concerns I foresee.

* Use semantic HTML: form, fieldset, legend, label, and appropriate input types.
* Every input must have an explicitly associated label.
* Use accessible names for all controls (no unlabeled icon-only buttons).
* Validation errors must:
  * Be programmatically associated to the relevant field via aria-describedby (or equivalent),
  * Set aria-invalid="true" on invalid fields,
  * Appear in a summary region at the top on submit that links to each invalid field.
* Dynamic sections (Delivery Address and Card fields) must:
  * Be toggled without losing user-entered values,
  * Update visibility in a way that works for assistive tech (e.g., hidden / aria-hidden used correctly),
  * Move focus appropriately when a section is revealed or removed (focus the first newly-required field).
* Live “Order Summary” updates must be announced politely:
  * Use an aria-live="polite" region and avoid excessive spam (debounce updates to at most ~4 per second).
* Keyboard requirements:
  * Full operation with keyboard only,
  * Logical tab order,
  * Clearly visible focus indicator (do not remove outlines unless replaced with an obvious style).
* Color/contrast:
  * Do not rely on color alone to convey errors,
  * Ensure text and essential UI elements have strong contrast against backgrounds.
* Confirmation view:
  * Must have a clear heading,
  * Focus should move to the confirmation heading on successful submit.

Code quality expectations

* Keep code well-structured:
  * Separate logic into functions (pricing, validation, rendering summary, submit handling).
  * Avoid global variables where possible.
  * Add brief comments explaining the main logic.
  * Use responsive layout so it looks reasonable on mobile and desktop.
