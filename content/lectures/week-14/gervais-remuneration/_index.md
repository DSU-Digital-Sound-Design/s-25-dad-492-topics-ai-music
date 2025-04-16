+++
title = "The Remuneration Of Music Creators for the Use of Their Works by Generative AI"
outputs = ["Reveal"]
[reveal_hugo]
theme = "serif"
margin = 0.2
+++

# AI, Music, & Money

## Paying Music Creators for the Use of Their Works by Generative AI

{{% note %}}
Welcome everyone. Today we're discussing a hot topic: how artificial intelligence, specifically Generative AI, impacts music creators and how they should be compensated. This is based on a recent white paper by Prof. Daniel Gervais.
{{% /note %}}

---

## Author's Purpose

*   **The Challenge:** How to ensure ongoing payment for music creators when their existing music trains (or has been used to train) AI models?
*   **The Goal:**
    1.  Explain the technology (GenAI) and current copyright law.
    2.  Propose a **new right** for creators focused on fair compensation.

{{% note %}}
The paper tackles a big problem: AI learns from vast amounts of existing music, often without payment. The author wants to find a sustainable way forward, proposing a new legal tool rather than just applying old rules that might not fit perfectly. The focus is on the *idea* of the new right, not yet the exact legal wording.
{{% /note %}}

---

## The Music Creator's View (CIAM)

*   **Support Existing Rights:** All current copyright protections should apply to AI uses.
*   **Propose NEW Right:** An *additional* right of remuneration (payment) for the *ongoing use* of human works by AI platforms.
*   **Demand Transparency:** AI platforms *must* track and report which human works they use. Attribution is key for fair payment.

{{% note %}}
From the perspective of music creators (represented here by CIAM), existing rights are crucial, but likely not enough. They advocate for a *new layer* of protection specifically designed for how AI operates – focusing on payment when AI uses their work. Transparency is non-negotiable for making this work.
{{% /note %}}

---

## Executive Summary: The Problem

*   Generative AI challenges human creativity (music, art, writing).
*   Creators hone their craft over time, often needing to earn a living from it.
*   AI uses creators' existing work ("datasets") to generate new "content" that *competes* with them.
*   **Aim:** Find a way for creators to get paid when their work is used by AI, allowing them to retain agency.

{{% note %}}
The core issue: AI systems learn from human creations and then produce outputs that can directly compete in the marketplace with those same humans. The paper seeks a way to ensure creators benefit from this use, rather than just being replaced by technology trained on their own labor. The paper *doesn't* aim to stop AI, but to make it coexist fairly.
{{% /note %}}

---

## Executive Summary: Proposed Solution Concept

*   **Pay for Use:** Creators should be paid when AI systems *use* the datasets (containing their work) to generate new output.
*   **Mechanism:** This payment should take the form of a **license**.
*   **Requirement:** To license something, there must be a **right** that *can* be licensed.

{{% note %}}
The fundamental idea proposed is a shift: compensation isn't just about the initial training, but about the *ongoing value* derived when the AI *uses* that training data to create something new. This requires establishing a clear legal right that triggers the need for a license and payment.
{{% /note %}}

---

## Executive Summary: Legal Issues

Two key stages with potential copyright implications:

1.  **Training ("Input"):** AI models are *trained* on vast datasets. This involves making copies (**Text and Data Mining - TDM**).
2.  **Generation ("Output"):** Users prompt the AI, which then *produces* new content based on its training.

**Both stages can potentially infringe copyright.**

{{% note %}}
Legally, we need to look at two distinct moments. First, the "learning" phase where AI developers copy massive amounts of data. Second, the "creation" phase where the AI generates text, images, or music. Both involve potential use of copyrighted material.
{{% /note %}}

---

### Copyright Basics: Exclusive Rights

Copyright owners generally have exclusive rights to:

*   **(1) Reproduce** the work (make copies)
*   **(2) Prepare Derivative Works** (adaptations, arrangements, translations)
*   (3) Distribute copies
*   (4) Perform the work publicly (for music, drama, etc.)
*   (5) Display the work publicly
*   (6) Perform sound recordings publicly via digital transmission

*See: [17 U.S.C. § 106](https://codes.findlaw.com/us/title-17-copyrights/17-usc-sect-106/)*

{{% note %}}
Copyright law gives creators control over how their works are used. For AI, the rights of **reproduction** (copying during training and potentially in output) and **derivative works** (is the AI output an adaptation?) are most relevant. These are *exclusive* rights, meaning you need permission (a license) unless an exception applies.
{{% /note %}}

---

### Copyright Basics: What's *Not* (Easily) Protected?

*   **Exceptions (e.g., Fair Use):** In the US, "Fair Use" might allow limited copying for purposes like criticism, commentary, teaching, or research. Its application to AI training is highly debated and uncertain.
    *   *See: [Fair Use FAQ (U.S. Copyright Office)](https://www.copyright.gov/help/faq/faq-fairuse.html)*

{{% note %}}
There are limits to copyright. Fair Use is a major exception in the US, but it's a complex balancing test, and courts are still figuring out how it applies to AI training. Critically, you can't copyright a *style* (like "write a song in the style of The Beatles"). You copyright the specific song *they* wrote. This difference is crucial for AI, which often mimics styles. Note the difference between copyrighting the sheet music/lyrics (Composition) vs. a specific recording (Sound Recording).
{{% /note %}}

---

*   **"Style" or "Sound":** Copyright generally protects the specific *expression* (melody, lyrics, recorded sounds), not the underlying idea, genre, style, or a general "sound" or voice.
    *   *Musical Compositions (Music/Lyrics): [copyright.gov/circs/circ50.pdf](https://www.copyright.gov/circs/circ50.pdf)*
    *   *Sound Recordings (Recorded Performance): [copyright.gov/circs/circ56.pdf](https://www.copyright.gov/circs/circ56.pdf)*

---

## Discussion Question 1

1.  Is it fair for AI companies to train models on vast amounts of copyrighted music without asking for permission or paying creators? Why or why not?
2.  Should an AI be allowed to generate music that perfectly mimics a specific artist's unique "sound" or vocal style, even if it doesn't copy their exact songs?

{{% note %}}
Let's pause and discuss. Consider the arguments for innovation vs. creator rights. Think about the difference between being inspired by someone's style (like humans do) and an AI statistically replicating it based on analyzing thousands of their songs. Where do we draw the line?
{{% /note %}}

---

### Part I: How Generative AI Works (Simplified)

*   **Generative AI (GenAI):** AI that *creates* new content (text, images, music).
    *   Examples: ChatGPT (text), DALL-E (image), various music AI tools.
*   **Models:**
    *   **LLMs (Large Language Models):** Trained on text (e.g., GPT).
    *   **Diffusion Models:** Often used for images/video.
*   **Training:** Requires massive computing power and huge datasets. Often dominated by large tech companies.

{{% note %}}
GenAI isn't just analyzing data; it's *making* things that seem original. The "Large" in LLM is key – these models are trained on internet-scale data, which inevitably includes copyrighted material. This scale makes it hard for smaller players to compete.
{{% /note %}}

---

### Part I: The Training Process - Copying & Tokenizing

1.  **Copying:** Data (music files, text, images) is typically *copied* locally for efficient training.
2.  **Tokenizing:** The copied data is broken down into smaller pieces called "tokens".
    *   For text: tokens might be words, parts of words, or characters.
    *   For music: tokens might represent notes, chords, timings, or audio features.
3.  **Relationships:** The AI learns patterns and relationships *between* these tokens.

{{% note %}}
A crucial point: Training *starts* with copying the original work. Then, it's broken into 'tokens'. Think of tokens like tiny puzzle pieces. The AI doesn't just memorize the pieces; it learns how they fit together based on the original works.
{{% /note %}}

---

## Part I: Training Misconception

*   **Myth:** Training *destroys* the original work, leaving only abstract learning.
*   **Reality:** The process *preserves* representations (embeddings/vectors) of the original data, including relationships between elements.
    *   This allows the AI to *reproduce* parts of the training data or generate statistically similar content.
    *   The tokenized dataset *itself* can be seen as another reproduction.

{{% note %}}
It's NOT like a human reading a book and forgetting the exact words but remembering the plot. The AI retains detailed numerical representations (embeddings) linked to the tokens. These representations effectively store information derived directly from the copyrighted works, which is why the AI can sometimes regurgitate training data. This makes the tokenized dataset legally significant.
{{% /note %}}

---

## Part I: How AI Generates Output

*   **Prediction Machine:** Based on a prompt (user request), the AI uses its training (the learned relationships between tokens) to predict the most likely *next* token (word, note, pixel).
*   It does this repeatedly to generate a sequence (sentence, melody, image).

{{% note %}}
Think of it like super-advanced autocomplete. If you type "Twinkle, twinkle, little...", the AI predicts "star" is the most probable next word based on everything it read during training. It applies this prediction process sequentially to build up the final output.
{{% /note %}}

---

### Part I: Legal Implications of Tech

*   **Copying (Reproduction):**
    *   Initial copying for training.
    *   The tokenized dataset itself.
    *   Outputs that are substantially similar to training data.
*   **Rights Management Information (RMI):** Metadata (author, title, etc.) is often stripped during training, potentially violating laws like the DMCA in the US.
*   **AI Company Indemnification:** Offers from companies (like Google, Microsoft, OpenAI) to protect users from copyright lawsuits often have significant limitations and exclusions.

{{% note %}}
The technology has direct legal consequences. Multiple stages involve potential 'reproduction'. Removing metadata is another potential legal issue. And don't rely solely on the AI company's promise to cover legal fees – read the fine print!
{{% /note %}}

---

## Part I: Key Takeaways Summary

1.  Training LLMs involves **copying** data.
2.  Copying copyrighted data infringes rights unless an **exception** (like fair use) applies (highly debated).
3.  **Tokenization** also creates a reproduction, preserving aspects of the original works.
4.  AI **outputs** can infringe if substantially similar or derivative of training data.


{{% note %}}
To recap Part I: AI training heavily relies on copying copyrighted works in multiple ways. While exceptions like fair use exist, their application is unclear. Both the training process and the outputs can lead to copyright infringement. AI companies' legal protections for users aren't ironclad. Any new laws allowing TDM face international legal constraints.
{{% /note %}}

---

5.  Training may involve illegal **removal of RMI** (metadata).
6.  AI company **indemnification offers** have significant limits.
7.  Any legal **exception** for TDM must likely pass the international "three-step test" (balancing creator rights and public interest).

---

## Discussion Question 2

*   Does understanding *how* LLMs work (copying, tokenizing, preserving relationships, predicting) change your view on whether using copyrighted music for training is fair or constitutes infringement?
*   How is AI "learning" different from human learning in a way that matters for copyright?

{{% note %}}
Let's discuss the process. Does the fact that it's based on direct copying and statistical prediction, rather than human-like understanding or inspiration, make a difference legally or ethically? How does machine 'learning' compare to how a human musician learns from others?
{{% /note %}}

---

## Part II: Copyright Has Always Adapted

*   Copyright law isn't static; it evolves with technology:
    *   Player Pianos -> Mechanical reproduction rights
    *   Radio/TV -> Broadcasting rights
    *   Cinema -> Film recognized as copyrighted work
    *   Internet -> Digital transmission / "Making available" rights (WCT/WPPT 1996)
*   New rights (exclusive or remuneration) were often created to ensure creators were compensated for new major uses.

{{% note %}}
History shows us that copyright law has repeatedly adapted to major technological shifts. From player pianos to the internet, new ways of using creative works led to updates in the law to ensure creators could still control and benefit from their work. AI is arguably the next big shift requiring adaptation.
{{% /note %}}

---

## Part II: Why Adapt Now for AI?

*   AI is a profound technological change.
*   It uses creators' past work to generate *competing* content.
*   This threatens creators' ability to earn a living, potentially shrinking future creativity.
*   Delegating human interpretation/creation to machines has deep cultural implications.
*   **Goal:** Not to *stop* AI, but to ensure human creators can coexist and thrive alongside it, using the established system of copyright.

{{% note %}}
The argument is that AI isn't just another tool; it's a system trained on the entire history of human creation that can now automate parts of that creation, directly competing with human creators. This poses an existential threat that requires a specific response to maintain a creative ecosystem. The paper argues for adapting copyright, not abandoning it or trying to halt AI development.
{{% /note %}}

---

## Part II: The Proposal - A Right to Remuneration

*   **Create a NEW right** specifically for creators.
*   **What it covers:** Payment (remuneration) for the *use* of copyrighted material *within* an AI model when that model is used to *generate competing content*.
*   **Distinction:** This focuses on the *output* phase's reliance on the training data, not just the initial *input* copying (which is covered by existing reproduction rights).

{{% note %}}
Here's the core proposal: A new, specific legal right. It's not about stopping the AI training, but about triggering a payment obligation when the trained AI is *used commercially* to produce outputs that compete with human creators. It acknowledges the value creators' works provide to the AI *after* training.
{{% /note %}}

---

## Part II: Advantages of This Proposed Right

*   AI training can continue largely **unhindered**.
*   AI companies **pay** for a key, valuable input (the creative data).
*   **Exempts non-commercial research** uses (e.g., universities).
*   **Compensates creators** when AI uses their life's work to *compete* with them.

{{% note %}}
This approach aims for balance. It avoids blocking AI development by allowing training to continue (subject to existing copyright rules). It targets commercial exploitation that directly impacts creators' livelihoods. It ensures AI companies pay for the valuable human creativity fueling their systems, while carving out exceptions for beneficial research.
{{% /note %}}

---

## Part II: Legal Details - Subject Matter & Ownership

*   **Applies to:** Copyright-protected musical works (likely compositions first).
*   **Initial Owner:** The human creator(s).
*   **Transferable:** Creators could assign or license this right (e.g., to publishers, CMOs).
*   **Normative Basis:** Empowers creators, giving them agency when their work fuels competing AI output.

{{% note %}}
This new right would attach to the copyrighted work itself, like other copyright facets. Crucially, it would initially belong to the human creator, reinforcing the principle of author's rights. Like other rights, it could then be managed through agreements or collective organizations (CMOs).
{{% /note %}}

---

## Part II: Legal Details - National Treatment

*   **If "Sui Generis" (Unique Right):** Countries could choose *reciprocity* (only pay creators from countries with a similar right). This incentivizes other countries to adopt it.
*   **If Part of Copyright:** Subject to *national treatment* (must treat foreign creators the same as domestic ones, under treaties like Berne/TRIPS).

{{% note %}}
This is a technical but important point. If the new right is legally separate from traditional copyright ('sui generis'), countries could make deals based on mutual adoption. If it's considered an extension of copyright, existing treaty rules requiring non-discrimination would likely apply. The legal structure matters for international implementation.
{{% /note %}}

---

### Part II: Legal Details - Compulsory License? Levy?

*   **Remuneration Right:** Can be structured similar to existing compulsory/statutory licenses (use allowed if payment made), which is generally permissible under international law.
*   **Better than a Levy:** A simple levy (like on blank tapes/hard drives) based on *input* data size doesn't reflect *actual use* or market impact of the AI output. The proposed right connects payment more directly to the AI's productive use.

{{% note %}}
The proposal leans towards a right to be paid *for use*, potentially managed like systems where certain uses are allowed by law as long as a fee is paid (compulsory license). This is seen as fairer than a simple tax on AI training (levy) because it tries to link payment to how much the AI actually *generates* potentially competing content using the training data.
{{% /note %}}

---

## Part II: Practicalities - The Distribution Challenge

*   **Common Argument Against:** How can we possibly track which works were used by the AI to generate a specific output and distribute the money fairly? It's too complicated!

{{% note %}}
A major hurdle for any payment system like this is the practical side. Critics often argue that tracking the influence of millions of training inputs on countless AI outputs is technically infeasible or impossibly complex, making fair distribution a fantasy.
{{% /note %}}

---

#### Part II: Practicalities - Potential Solutions

*   **Transparency is Key:** AI platforms *can* be designed to identify source material or influences (though they may resist). Requires legal obligation.
    *   EU AI Act mandates *some* training data disclosure.
*   **CMOs:** Collective Management Organizations already distribute royalties based on complex usage data/proxies. They have experience.
*   **Usage Data:** Ideally, track how often tokenized works are "pulled" by the AI during generation.
*   **Proxies:** If direct tracking is impossible, use proxies (like commercial success of source works, genre representation in dataset).
*   **Focus:** Ensure money reaches *individual creators*.

{{% note %}}
The paper argues the "too complicated" argument is defeatist. Technology *can* provide more transparency if required by law. Existing organizations (CMOs) handle complex royalty distributions already. While perfect tracking might be hard, good systems based on available data (ideally direct usage, or proxies if needed) are possible. The EU's move towards transparency is a step in this direction. The ultimate goal is fair payment reaching the original creators.
{{% /note %}}

---

## Discussion Question 3

*   How could we realistically track AI's use of specific songs or musical elements to pay creators fairly?
*   What are the pros and cons of relying on Collective Management Organizations (CMOs) versus requiring AI companies themselves to provide detailed usage data for distribution?

see: [CMOs - Collective Management Organizations - CLIP](https://goclip.org/en/music/the-ecosystem/what-are-cmos?utm_source=chatgpt.com)

{{% note %}}
Let's brainstorm practical solutions. What technology might help? What data would be needed? Who should manage the money collection and distribution – established music industry bodies (CMOs) or should the AI companies handle it? What are the risks and benefits of each approach (e.g., efficiency, bias, conflicts of interest)?
{{% /note %}}

---

### Conclusion

*   Generative AI poses a significant challenge and opportunity for music creators.
*   Existing copyright law offers partial solutions but may not be sufficient for ongoing, fair compensation.
*   A **new right of remuneration**, focused on payment when AI *uses* training data to generate competing content, is proposed.
*   This requires **transparency** from AI platforms and robust **distribution** mechanisms.
*   The goal is to adapt copyright to balance AI innovation with the sustainable livelihoods of human creators.

{{% note %}}
In summary, AI's use of music requires a response. The paper argues that simply applying old laws isn't enough. A new, tailored right focused on payment for the AI's *productive use* of training data seems necessary. Making this work hinges on transparency and effective systems to get payments to creators. It's about finding a path forward where both technology and human creativity can flourish. Thank you.
{{% /note %}}