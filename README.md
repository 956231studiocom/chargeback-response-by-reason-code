# Chargeback Response: What to Send by Reason Code

A reference for store owners who just opened a dispute notice and have a short window to answer it.

Most chargebacks are not lost on the facts. They are lost **by default** — because the response arrived late, because it argued about store policy instead of the transaction, or because the evidence that would have won it was purged weeks earlier.

This covers the three things that decide the outcome: **what evidence a processor actually accepts per reason code**, **what the first hour should look like**, and **what to keep before you need it**.

> Not legal advice, no guarantee of outcome. Issuers and processors decide. The goal is narrower: do not lose by default.

---

## The three ways people lose without being wrong

**1. They argue policy.**
"I clearly state no refunds on the product page" is not evidence about the transaction. Dispute rules ask whether the cardholder authorised the charge and received what was described — not what your terms say. Policy arguments consume the word limit and prove nothing.

**2. They attach screenshots instead of records.**
A screenshot of a tracking page is a picture. A tracking record with the carrier's response, timestamp, destination and signature is evidence. Processors are auditable systems; they want the second kind.

**3. They answer late.**
The response window is counted in calendar days. Miss it and the dispute resolves against you before anyone reads the file.

---

## What each reason code actually wants

### `fraudulent` — "card not authorised"

Whether the real cardholder made the purchase:

- AVS result and CVV result as returned by the processor — not your assumption about them
- IP address, device fingerprint and geolocation at the moment of order
- Delivery confirmation to the billing address, or to an address the customer confirmed in writing
- Prior order history from the same cardholder with no disputes
- For digital goods: download logs with timestamps, IP and account email

Ignored: "the order looks normal", fraud scores with no fields attached.

### `product_not_received`

A logistics question:

- Carrier tracking record showing delivery, with timestamp and destination postal code
- Proof of delivery: signature, photo, or carrier confirmation
- The shipping address exactly as the customer entered it
- Communication showing the customer acknowledged delivery

Ignored: a tracking link with no snapshot of what it said at the time.

### `product_not_as_described` / `unacceptable`

A description-versus-reality question:

- The product page as it existed at purchase time — archived, not "what it says now"
- Order details showing variant, size, colour, quantity shipped
- The customer's own messages, if they describe something different from what was shipped
- Your return/refund record, if a return was offered and declined

Ignored: your opinion that the product was fine.

### `duplicate_charge`

Usually technical, not judgemental:

- Both transaction records with distinct authorisation codes
- Evidence they are for different orders, or that one was voided/refunded
- The processor's settlement report for the period

### `subscription_canceled`

Whether cancellation was available and whether it happened before the charge:

- The cancellation flow as the customer experienced it, with timestamps of any attempt
- Login and click records around the alleged cancellation
- Your cancellation confirmation email, or the absence of a request
- Billing terms shown at signup, archived

### `credit_not_processed`

Whether you promised a refund and failed to issue it:

- Refund transaction ID and settlement date
- The processor's refund record
- If the refund was issued after the dispute: the transaction reference, so the issuer can close it

---

## The first hour

Do these before writing a word of response:

1. **Pull the transaction record.** Authorisation code, AVS/CVV result, IP, device, timestamp, amount, currency.
2. **Export the tracking record now.** Carrier page, API response, or both — with today's date visible, because the carrier will purge it.
3. **Save the delivery confirmation**, and download the underlying record if the API exposes it.
4. **Check whether the customer contacted you first.** An unanswered support email before the dispute is a very different story from silence.
5. **Read the reason code, not the customer's message.** The code defines which evidence matters.

Then write the response: short, factual, numbered against the code's requirements, no emotion, no legal threats.

---

## What to keep, before you need it

| Record | Typical retention | Why it matters |
|---|---|---|
| Carrier tracking | ~60 days at many carriers | Most requested evidence for "not received" |
| Product page snapshot | Keep your own, indefinitely | "As described" disputes are decided on the page **at purchase time** |
| Checkout terms shown to buyer | Keep your own | Needed for subscription and refund disputes |
| Order export | Monthly | Your only copy independent of platform uptime |
| Support correspondence | 12 months minimum | Pre-dispute contact changes the narrative |

The failure mode is consistent: the dispute arrives on day 75 and the tracking record died on day 60. Export on a schedule, not on demand.

---

## Full kit

This repo is the framework. The paid kit adds what you paste into an actual response:

- **Evidence pack template per reason code** — six sections, each listing exactly which documents a processor accepts and which get ignored
- **Reply letter skeletons per code** — short, factual, structured so a reviewer can verify each claim against an attached record
- **Retention calendar** — what to export and how often, so evidence exists at the moment of the dispute

<https://475563839418.gumroad.com/l/shopify-chargeback-response-kit>

The kit's deliverable is readable **before** you pay: <https://956231studio.com/deliverables/shopify-chargeback-response-kit.html>

Related, free: the 15-check [store ops daily checklist](https://github.com/956231studiocom/store-ops-daily-checklist) covers the operational leaks that turn into disputes.

---

## Contributing

If a reason code has an evidence requirement not covered here, open an issue with the code name, processor, and which document the reviewer actually accepted. Concrete cases get added.

## License

CC BY 4.0 — copy, translate, reuse with attribution.
