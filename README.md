# Title: Spectral Isolation Equalizer

## Field of the Invention
This invention relates to audio signal processing, particularly equalization techniques that dynamically allocate spectral space across multiple tracks in a mix through inter-instance communication.

## Background
Audio mixing requires careful spectral balancing to prevent frequency masking between tracks. Traditional equalizers allow manual adjustments of gain at different frequency bands, but they do not facilitate **real-time, inter-instance spectral negotiation** between multiple tracks. This limitation often results in a time-consuming, iterative process for sound engineers.

Existing solutions, such as iZotope Neutron’s "Unmask" feature and FabFilter Pro-Q 3’s spectrum visualization, offer some cross-track awareness but lack **simultaneous, proportional cut-and-boost automation** across multiple equalizer instances.

## Summary of the Invention
The **Spectral Isolation Equalizer (SIEQ)** introduces a novel **inter-instance communication system** that allows multiple instances of the equalizer plugin to dynamically negotiate spectral space. This ensures that:

- Boosts applied on a source track are **automatically counterbalanced** by proportional cuts on competing tracks.
- A user-defined **cut ratio** determines the extent of attenuation applied to competing tracks.
- The system provides real-time visualization and control over inter-instance adjustments.
- Center frequency and Q values remain under the user’s control, ensuring **musical integrity**.

The **technical advantage** is the automation of spectral negotiation across tracks, eliminating the need for **manual EQ carving** while maintaining artistic control.

## Detailed Description
### System Architecture
Each **instance** of the Spectral Isolation Equalizer operates within a **shared processing network** across multiple tracks within a digital audio workstation (DAW). The system comprises:

1. **Inter-Instance Communication Module:** Tracks EQ changes in real-time across instances.
2. **Proportional Cut Engine:** Applies frequency cuts based on a **user-defined ratio** (e.g., 1:1, 2:1, 3:1) when another instance applies a boost.
3. **Centralized Frequency Management:** Maintains coherence between **center frequency selections and Q values**, avoiding phase cancellation.
4. **User Interface:** Provides intuitive control over real-time frequency interactions.

### Operational Workflow
1. **Instance Initialization:** Each instance registers itself within the DAW session and listens for spectral activity from other instances.
2. **Spectral Adjustment Detection:** If a **boost** is applied on one track, the system calculates compensatory cuts on competing tracks using the **Proportional Cut Engine**.
3. **Inter-Instance Adjustment Execution:** The cuts are applied dynamically while maintaining transparency in the mix.
4. **User Override & Customization:** Engineers can manually override proportional adjustments if artistic preferences require fine-tuning.

### Example Use Case
1. A **vocals track** is boosted at **3 kHz** for presence.
2. The SIEQ detects that the **guitar track** also contains energy at **3 kHz**.
3. Based on the **user-defined ratio (e.g., 2:1)**, a **-3 dB boost** on vocals triggers a **-6 dB cut** on the guitar track at 3 kHz.
4. The result is **enhanced clarity without manual EQ carving**.

## Claims
1. A method for real-time spectral isolation in audio mixing, comprising:
   - Applying **simultaneous frequency boosts and cuts** to allocate spectral space within a mix;
   - Facilitating **inter-instance communication** across multiple instances of the equalizer;
   - Dynamically adjusting **gain reduction on competing tracks** in response to boosts on a source track.

2. The method of claim 1, wherein the **gain reduction** is based on a **user-defined cut ratio**.

3. The method of claim 1, further comprising **real-time spectral visualization** for enhanced user control.

4. A system for spectral equalization, comprising:
   - A **plugin framework** allowing multiple instances to communicate within a DAW;
   - A **Proportional Cut Engine** for automatic gain reduction calculations;
   - A **centralized frequency management system** for maintaining musical integrity.

5. The system of claim 4, wherein adjustments are applied dynamically without **manual EQ intervention**.

6. A non-transitory computer-readable medium storing instructions that, when executed, cause a processor to perform spectral equalization, the instructions comprising:
   - Identifying **boosts on a source track**;
   - Applying **compensatory cuts** on competing tracks;
   - Adjusting **gain values dynamically** based on a user-defined cut ratio.

## Open Source Licensing Model
This software is licensed under the **Spectral Isolation Equalizer Open Source License (SIEQ-OSL v1.0)**.

### **1. Permitted Free Use (Non-Commercial)**
✅ Individuals, hobbyists, and **non-commercial projects** may use, modify, and share this software **freely** without restriction.
✅ Open-source projects incorporating this code must **retain this license and credit the original author**.

### **2. Commercial Use & Attribution Requirements**
For **commercial use** (i.e., selling, distributing, or otherwise monetizing a product based on this software), the following conditions apply:

#### **2.1 Attribution Requirement**
- Any commercial product that includes, extends, or is **inspired by** the Spectral Isolation Equalizer must **credit** the original creator as follows:
  - In the **About Section** of the software or plugin UI:
    - “This product is based on the Spectral Isolation Equalizer, originally developed by [Your Name].”
  - In any **public-facing documentation or marketing material**, credit must be included.

#### **2.2 Revenue Share Requirement**
- Companies or individuals generating **$100,000 USD/year or more** in gross revenue from software implementing this concept **must pay a 5% revenue share** on any income directly related to the Spectral Isolation Equalizer's implementation.
- Revenue share is **capped at $1,000,000 per year per company**.
- Payment is due **quarterly**, with reports submitted detailing revenue calculations.

## Conclusion
The **Spectral Isolation Equalizer** is a pioneering advancement in audio equalization, introducing an automated approach to inter-track spectral balancing. By enabling **real-time inter-instance communication**, it significantly enhances mixing efficiency while preserving **creative control** over sound design.



--------------------------

# NOTICE NOTICE NOTICE: the stuff below is just so i remember how to deploy the site!

This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/basic-features/font-optimization) to automatically optimize and load Inter, a custom Google Font.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.
