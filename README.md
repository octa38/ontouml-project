# OntoUML Model: GP Office Healthcare Scenario

A project modeling the healthcare process around General Practitioner (GP) offices in the Netherlands, built using an ontology-driven conceptual modeling approach (OntoUML). The goal was to make the concepts, relationships, and constraints of this domain explicit and easy to reason about.

## Authors

- Octaviana Cheteles (s2854740)
- Paola Joza (s2712016)
- Daan Schram (s2692759)

June 2025

## Overview

The domain covers the full journey of a patient interacting with the Dutch primary care system: calling to book an appointment, the internal structure and staffing of a GP office, and the process of getting a prescription filled at a pharmacy. Three separate diagrams were built to keep each part of the process clear and manageable, rather than cramming everything into one massive model.

Domain research was informed by public guidance from Thuisarts.nl and Zorgwijzer.nl.

## The Three Models

### 1. Calling for an Appointment

Covers how a registered patient contacts the GP office to book an appointment. Key concepts include:

- **Registered Patient**, who can be an Adult or a Minor, and Ill or Healthy
- **GP Assistant**, who takes the call
- **Legal Guardian**, required for minors under 16 to provide Parental Consent
- **Healthcare Professional**, who the appointment is eventually made with
- Relators tying these together: Call, Registration, Parental Consent, Employment Contract, and Appointment

### 2. Organization at the GP's Office

Models the internal structure of Dutch primary care: Healthcare Centers, Medical Practices (Solo or Group), and GPPost (the after-hours emergency network). It also covers the different staff roles found at a practice:

- **GP Assistant (Dokterassistent)**, first point of contact, handles admin and minor treatments
- **POH-S**, somatic practice assistant (diabetes, asthma, lung disease, etc.)
- **POH-GGZ**, mental health practice assistant
- **On-call GP**, rotating staff covering after-hours shifts under a temporary contract

### 3. Pharmaceutical Process

Follows a prescription from creation to dispensation:

- A **General Practitioner** issues a **Prescription** for a **Patient**
- A **Pharmacy** employs **Pharmacists** and **Pharmacy Assistants**, tracked via historical roles so the system knows exactly who approved and who dispensed each prescription
- **Prescription Validation** confirms the prescription is appropriate before anything is dispensed
- **Dispensation** happens either in person or via a Collecting Machine
- **Pharmacy Stock** tracks medication inventory per pharmacy

## Patterns Used

Each model was analyzed for common OntoUML design patterns, including:

- **Phase patterns** (e.g. Minor/Adult, Healthy/Ill), always disjoint and complete
- **Role patterns**, where an entity's identity depends on a relational context (e.g. GP Assistant, Historical Pharmacist)
- **Relator patterns**, connecting two entities through a mediating relationship (e.g. Call, Employment Contract, Prescription)
- **Subkind patterns**, where a more specific type inherits from a general kind (e.g. Pharmacy as a subkind of Organization)
- **Event patterns**, capturing things that happen rather than things that persist (e.g. Dispensation)

Diagrams highlighting each of these patterns are included alongside the base models for reference.

## Tools

Diagrams were built with Visual Paradigm Community Edition.

## References

1. Thuisarts.nl, "How can I ask my GP questions or make an appointment?" https://www.thuisarts.nl/, accessed May 2025.
2. Zorgwijzer, "Healthcare in the Netherlands (Dutch system)." https://www.zorgwijzer.nl/, accessed May 2025.
