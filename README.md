# stagecraft-day0-fixture

Throwaway fixture repository for the **Stagecraft Day-0 gate** (charter §10):
a Jenkins declarative pipeline with three stages — `Checkout`, `Build`,
`Deploy to staging` — where the third stage fails on purpose.

Consumed by the multibranch job of a throwaway local Jenkins container used
only for API verification. Not a product artifact.
