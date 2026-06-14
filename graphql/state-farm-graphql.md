# State Farm GraphQL Schema

## Overview

State Farm is the largest property and casualty insurance provider in the United States, offering auto, home, renters, life, health, business, and farm/ranch insurance through approximately 19,000 agents. This conceptual GraphQL schema models the insurance domain exposed through State Farm's Partner Gateway developer portal at developer.statefarm.com, which provides REST APIs for partners, agents, and third-party platforms.

State Farm's external API access is limited to vetted partners via the developer portal. The REST APIs support renters insurance quoting and policy management, auto insurance quoting and policy inquiry, and B2B insurance verification for lenders and mortgage servicers. This GraphQL schema is a conceptual representation of the underlying insurance domain, not a published GraphQL endpoint.

## Schema Source

Conceptual schema derived from:

- State Farm Developer Portal: https://developer.statefarm.com
- State Farm Renters Insurance API documentation
- State Farm Auto Insurance API documentation
- State Farm B2B Insurance Inquiry API documentation
- State Farm public product and coverage documentation at statefarm.com

## Types

### Policy Types

- **Policy** — Base policy entity with policy number, status, effective and expiration dates, premium, and links to policyholder and coverages.
- **AutoPolicy** — Auto insurance policy extending Policy with vehicle list, drivers, telematics enrollment, and Drive and Save program participation.
- **HomePolicy** — Homeowners insurance policy with dwelling address, replacement cost, flood/earthquake riders, and mortgage holder information.
- **LifePolicy** — Life insurance policy with face value, beneficiaries, policy riders, cash value (for permanent products), and term details.
- **HealthPolicy** — Health insurance policy with plan type, network, deductibles, copays, and covered members.
- **RentersPolicy** — Renters insurance policy with personal property limit, liability limit, additional living expense coverage, and scheduled items.
- **BoatPolicy** — Watercraft and boat insurance policy with vessel information, agreed value or actual cash value, and navigational territory.
- **FarmPolicy** — Farm and ranch insurance policy with farmstead structures, farm equipment, livestock coverage, and crop details.
- **UmbrellaPolicy** — Umbrella liability policy providing excess liability over underlying auto, home, and other policies.
- **BusinessPolicy** — Business owners policy or commercial lines policy with business property, general liability, and business income coverage.

### Policyholder and Insured Types

- **PolicyHolder** — Primary named insured and account owner with contact information, policy list, and agent assignment.
- **NamedInsured** — Individual or entity formally named on the policy declarations page with insured status and relationship to account.
- **AdditionalInsured** — Third party added to a policy as an insured party, typically a lender, landlord, or business partner.

### Policy Structure Types

- **PolicyTerm** — Defined period of insurance coverage with start date, end date, term length, and associated premium.
- **Endorsement** — Policy modification or addition that changes the standard coverage terms, with effective date and premium impact.
- **PolicyRider** — Optional add-on benefit attached to a life or health policy, such as accidental death, waiver of premium, or long-term care.

### Coverage Types

- **Coverage** — Base coverage entity with coverage type, limit, deductible, and premium contribution.
- **AutoCoverage** — Auto-specific coverage container linking a vehicle to its applicable coverages.
- **LiabilityCoverage** — Bodily injury and property damage liability coverage with per-person and per-occurrence limits.
- **CollisionCoverage** — Coverage for vehicle damage resulting from collision with another vehicle or object.
- **ComprehensiveCoverage** — Coverage for vehicle damage from non-collision causes including theft, weather, and vandalism.
- **PIPCoverage** — Personal Injury Protection coverage for medical expenses and lost wages regardless of fault.
- **UMCoverage** — Uninsured Motorist coverage providing protection when the at-fault driver has no insurance.
- **UIMCoverage** — Underinsured Motorist coverage when the at-fault driver's limits are insufficient.
- **MedPayCoverage** — Medical Payments coverage for medical expenses for the insured and passengers.
- **HomeCoverage** — Homeowners coverage container with dwelling, personal property, and liability components.
- **DwellingCoverage** — Coverage for the physical structure of the insured home up to replacement cost.
- **PersonalPropertyCoverage** — Coverage for personal belongings inside the home or rented dwelling.
- **LossOfUseCoverage** — Coverage for additional living expenses when the home is uninhabitable due to a covered loss.

### Financial Types

- **LiabilityLimit** — Structured limit with per-person, per-occurrence, and aggregate amounts.
- **Deductible** — Amount the insured pays before insurance coverage applies, with split deductible options for named perils.
- **Premium** — Policy or coverage cost with base rate, discounts applied, surcharges, and final billed amount.
- **PaymentPlan** — Installment schedule for premium payment including due dates, amounts, and payment method.
- **AutoPayment** — Automatic payment enrollment configuration linking a bank account or card to a payment plan.

### Vehicle Types

- **Vehicle** — Insured vehicle with VIN, year, make, model, garaging address, and usage type.
- **VehicleInfo** — Decoded vehicle specifications from VIN including safety ratings, anti-theft features, and original MSRP.
- **VIN** — Vehicle Identification Number with decoded manufacturer, model year, assembly plant, and serial components.

### Driver Types

- **Driver** — Licensed driver on an auto policy with license number, state, date of birth, and relationship to policyholder.
- **DriverRecord** — Motor vehicle record summary with violation history, accident history, and license status.
- **DrivingHistory** — Historical driving record including violations, at-fault accidents, and claims attributed to the driver.
- **SafetyScore** — Telematics-derived driver safety score from the Drive and Save program based on driving behaviors.
- **DriveAndSave** — State Farm telematics program enrollment with device or app status, trip data, and earned discount.

### Claim Types

- **Claim** — Base claim entity with claim number, date of loss, loss description, status, and assigned adjuster.
- **AutoClaim** — Auto insurance claim with vehicles involved, accident details, police report, and repair status.
- **HomeClaim** — Homeowners or renters claim with property address, loss type, damage description, and contractor information.
- **ClaimStatus** — Current state of a claim through its lifecycle from first notice of loss to closure.
- **ClaimEstimate** — Repair or replacement cost estimate associated with a claim.
- **ClaimPayment** — Payment issued on a claim with payee, amount, payment method, and date.
- **ClaimAdjuster** — State Farm adjuster assigned to a claim with contact information and claim assignment list.

### Repair and Service Types

- **Repair** — Vehicle or property repair associated with a claim, tracking shop, status, and completion.
- **BodyShop** — Auto repair facility capable of handling State Farm claims.
- **PreferredShop** — State Farm Select Service preferred repair shop with quality guarantee and direct billing.
- **Rental** — Rental vehicle arranged under a claim with rental company, vehicle class, daily rate, and duration.

### Distribution Types

- **Agent** — State Farm agent with name, office address, phone, email, appointed states, and product lines.
- **AgentLocator** — Agent search result set based on ZIP code, city, or geolocation with distance sorting.

### API Access Types

- **APIKey** — Partner Gateway API credential with key identifier, scopes, rate limits, and expiration.
- **Token** — OAuth access token with bearer value, expiry, associated scopes, and refresh token.

## Queries

- `policy(policyNumber: String!)` — Retrieve a policy by policy number.
- `policies(policyHolderId: String!)` — List all policies for a policyholder.
- `vehicle(vin: String!)` — Look up vehicle information by VIN.
- `claim(claimNumber: String!)` — Retrieve a claim by claim number.
- `claims(policyNumber: String!)` — List claims for a policy.
- `agent(agentId: String!)` — Retrieve an agent by ID.
- `agentLocator(zipCode: String, latitude: Float, longitude: Float)` — Find agents near a location.
- `quote(type: PolicyType!, input: QuoteInput!)` — Request an insurance quote.
- `driveAndSave(policyNumber: String!)` — Retrieve telematics program details for an auto policy.

## Mutations

- `createRentersPolicy(input: RentersPolicyInput!)` — Initiate a new renters insurance policy application.
- `updatePolicy(policyNumber: String!, input: PolicyUpdateInput!)` — Update policy details or coverage selections.
- `fileClaim(input: ClaimInput!)` — Submit a first notice of loss to open a new claim.
- `updateClaim(claimNumber: String!, input: ClaimUpdateInput!)` — Update claim information.
- `enrollDriveAndSave(policyNumber: String!, driverId: String!)` — Enroll a driver in the Drive and Save telematics program.
- `addVehicle(policyNumber: String!, input: VehicleInput!)` — Add a vehicle to an existing auto policy.
- `addDriver(policyNumber: String!, input: DriverInput!)` — Add a driver to an existing auto policy.
- `setPaymentPlan(policyNumber: String!, input: PaymentPlanInput!)` — Update the payment plan for a policy.
- `enrollAutoPayment(policyNumber: String!, input: AutoPaymentInput!)` — Enroll in automatic premium payment.
